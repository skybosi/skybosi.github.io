# 关于Imaginer的功能开发进展表

1. 对bmp的图片的读取和像素操作
2. 简单通用的图片操作(缩放、平移、镜像等)，最主要的是椭圆化的功能(可以推广这类似的思想)
3. 像素相似度的初步计算方法
4. 像素突变点的识别  [diff][1]
5. 边界线获取方法的探讨和尝试及最终确定  [getedge][2]
6. 获取边界线以及防止重复获取同一边界线设置标志(详见Edge.bmp)  [Edge][3]
7. 为了实现抠图，对极点对的设置，曾经试着用三种方法，直到现在的方法
8. 添加对每一个边界点的方向、引用计数(现在被隐藏)、边界框FramePoint  [framePoint][4]
9. 实现抠图，边界高亮(由于工作而学习了Android & NDK，故开始构思ImaginerApp)  [ImaginerApp][5]
10. 添加通用处理功能——图片稀释(density),但似乎没什么用
11. 修改极点对的设置法及现在版本，同时发现整个代码结构过于臃肿
12. 在脑海试图代码重构计划，因此停止了github的代码更新  [recode][6]
13. ImaginerApp开始，为了提高效率和代码重用，使用jni，开始学习NDK & jni
14. ImaginerApp实现图片的加载和像素点的操作
15. 代码重构图出炉(详见recode.bmp)  [recode][6]
16. 开始代码重构，但是遇到不少困难，试图实现扩展性很强的结构设计
17. 数据提供者模块独立出来，可以不错的实现处理
18. 数据处理中心模块成型，并减少两模块的耦合，但还有改善余地
19. 实现画线(bresenham算法改，添加设置线宽)，画矩形功能
20. 增加画线的不同重载函数
21. 添加简易脑补算法，但有明显不足
22. 实现边界框的内抠图算法，边界框高亮
23. 增加边界框的位置关系检测
24. 试图通过边界框位置关系linker边界线，但未实现
25. 添加边界线的移动算法
26. 改进画线算法，改进边界线移动算法
27. 增加边界线放大算法，基本实现但有很多其他情况未考虑到，故效果不佳
28. 边界移动的碰撞问题算法 [peng][8]
29. 复杂的边界线及内部数据的移动细节问题
30. 添加边界点化和去近点毛刺的功能
31. 添加命名空间，改善代码结构
32. 修改颜色系统，增强可用性
33. 替换编译方式为cmake
34. 添加common功能灰度化(gray)
35. 新增iPoint模块，同时进行命名空间的清理，将像素的坐标独立出来，方便以后的坐标变换

# 关于Imaginer的功能开发进展中的bug
1. 对于非闭合边界线的不全问题，以及一次导致的FramePoint.setframePoint失败，进而引起的moveBoundary失败等一些列问题




[1]:https://github.com/skybosi/Imaginer/blob/devM/doc/diff.png "diff"
[2]:https://github.com/skybosi/Imaginer/blob/devM/doc/getegde.png "getegde"
[3]:https://github.com/skybosi/Imaginer/blob/devM/doc/Edge.png "Edge"
[4]:https://github.com/skybosi/Imaginer/blob/devM/doc/linker1.png "framePoint"
[5]:https://github.com/skybosi/ImaginerApp "ImaginerApp"
[6]:https://github.com/skybosi/Imaginer/blob/devM/doc/recode.png "recode"
[8]:https://github.com/skybosi/Imaginer/blob/devM/doc/%E7%A2%B0%E6%92%9E.png "peng"