# chap1 计算机网络和因特网

## 1.1 什么是因特网

公共因特网

所有的终端设备叫做主机（host）或者端系统（end system） 

端系统通过通信链路（communication link）和分组交换机连接到一起。

链路的传输速录通过bit/s bps来进行度量

发送数据的时候发送的是包（packet），发送端会给数据分段，并且给每一段加上首部字节。

![image-20230914112847067](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914112847067.png)

![image-20230914112935713](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914112935713.png)

![image-20230914113114085](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914113114085.png)

![image-20230914113213378](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914113213378.png)

### 1.1.2 服务描述

![image-20230914113436772](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914113436772.png)

![image-20230914113521326](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914113521326.png)

### 1.1.3 什么是协议

![image-20230914113729200](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914113729200.png)

一种好的行为方式

![image-20230914113834747](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914113834747.png)

> 协议定义了在两个或者多个通信实体之间交换的报文格式和顺序，以及报文发送和/或接受一条报文或其他事件所采取的动作。

## 1.2 网络边缘

> 端系统:包括桌面计算机，服务器和移动计算机，它们位于因特网的边缘，所以被成为端系统。

![image-20230914183425405](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914183425405.png)

ISP 一层一层向上走

端系统的别称是主机，因为他们运行应用程序，在本书当中，主机=端系统。主机又是又被进一步划分为两类，客户和服务器。客户就是我们常用的手机电脑，服务器通常是更加强大的机器，用于存储和发布web界面，中继电子邮件等等。

### 1.2.1 接入网

接入网是将端系统物理链接到其边缘路由器的网络。边缘路由器是端系统到任何其他远程端系统的路径上的**第一台路由器**。

1.家庭接入

DSL:本地电话公司是ISP,使用现有的电话线，分频率复用

DSL先将数字信号转化为高频音，也就是模拟信号，接收端DSLAM将模拟信号转化回数字信号。

![image-20230914215538861](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914215538861.png)

电缆因特网接入（cable internet access）

![image-20230914220029279](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914220029279.png)

电缆接入会共享广播媒体，也就是说几个用户一起下载东西的时候，网速会变慢。

FTTH:光纤到户，包括主动光纤网络和被动光纤网络，主动光纤网络本质是交换因特网。我们简要·讨论一下POM

![image-20230914220822241](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914220822241.png)

感觉寝室用的是这个，很快

#### 企业和家庭接入，以太网和wifi

![image-20230914221336965](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914221336965.png)

网线和wifi，相当于你的内部有一个小型网络，然后小形网络集散之后接入大型网络

#### 广域无限接入，3G和LTE

一个用户只需要位于基站的数万米范围之内

没说为啥

### 1.2.2 物理媒体

引导型媒体和非引导型媒体

引导型沿着线走，非引导性在空气中传播

![image-20230914222340903](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914222340903.png)

![image-20230914222829817](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914222829817.png)

![image-20230914222839161](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914222839161.png)

![image-20230914223029052](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914223029052.png)

radio

![image-20230914223351622](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914223351622.png)

同步卫星慢，近地卫星麻烦

## 1.3 网络核心

### 1.3.1 分组交换

![image-20230914223540753](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914223540753.png)

如果某个源端系统或分组交换机经过一条链路发送一个L比特的分组，链路的传输速率为R比特/秒，则传输该分组的时间为L/R秒

1.存储转发传输

必须要先完整接收到这个输入分组，才能进行输出。

![image-20230914224307851](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914224307851.png)

![image-20230914224905536](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914224905536.png)

第一次时间翻倍，但多了之后实际上是n+1这个量级。

![image-20230914225031869](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914225031869.png)

有n个中间点

P个分组就是

(P-1)L/R（最后一个晚出发了多久）+NL/R（一个数据跑一次要多久）

![image-20230914225314664](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914225314664.png)

丢包是因为包太多了

![image-20230914225336745](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914225336745.png)

#### 转发表和路由选择协议

![image-20230914225607307](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914225607307.png)

根据目的地ip地址的一部分，决定走那一条路

![image-20230914225749776](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914225749776.png)

### 1.3.2 电路交换

![image-20230914225936555](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914225936555.png)

电路交换网络相当于一种只接受预定的餐厅

![image-20230914230207973](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230914230207973.png)

类似于公交专用道

![image-20230915003404862](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230915003404862.png)

考虑频域图，横坐标轴找到一块宽度为4kHz小段。

![image-20230915003637236](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230915003637236.png)

分时复用相当于RR，ABCDABCD，一个帧实际上相当于一个循环节。

![image-20230915004121301](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230915004121301.png)

我们认为分组的策略更好，应为一般来说不会有那么多人同时使用。

![image-20230915004400470](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230915004400470.png)

能够更好的处理单人高爆发的情况

![image-20230915004605154](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230915004605154.png)

### 1.3.3 网络的网络

![image-20230915005216359](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230915005216359.png)

![image-20230915005122322](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230915005122322.png)

![image-20230915005445082](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230915005445082.png)

![image-20230915112004800](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230915112004800.png)

back up plan ，多个源头，一个坏了还能得到数据

![image-20230915005613688](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230915005613688.png)

不希望有中间商赚差价，于是有了对等市场

![image-20230915005759791](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230915005759791.png)

从你这里下基层要付费，我就自己下基层，但我自己下不完备，所以我依然和你合作

## 1.4 分组交换网中的实验，丢包和吞吐量

### 1.4.1 时延概述

主要是节点处理时延，排队时延，传输时延，传播时延。每个节点都会经历一次这些时延。

![image-20230915095607268](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230915095607268.png)

处理检查比特，决定走向的方向

![image-20230915095725749](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230915095725749.png)

![image-20230915150031550](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230915150031550.png)

不是说分组之后组就是一起走的，由于传输链路有速度限制，即使同一个组内的数据可能还是要慢慢通过这条路。

![image-20230915170452204](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230915170452204.png)

传文件的时间，受到文件大小的影响。

![image-20230917090918472](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230917090918472.png)

相当于“火车有多长”和“铁轨有多长”的问题

![image-20230917091654741](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230917091654741.png)

所有人都通过收费站之前，只允许在收费站等着

![image-20230917092011166](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230917092011166.png)

![image-20230917100631448](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230917100631448.png)

我们考虑最后一辆车

![image-20230917101440199](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230917101440199.png)

![image-20230917115754634](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230917115754634.png)

a:**平均**每秒来几个包

L:一个包几个bit

aL:每秒来几个比特

R:每秒走几个比特

![image-20230917120545183](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230917120545183.png)

注意LA/R是平均情况。相当于正态分布的对称轴，一旦出现对称轴右边的情况，就会排队

![image-20230917121050205](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230917121050205.png)

丢包是要补上去的！！！

### 1.4.3 端到端时延

![image-20230917123514520](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230917123514520.png)

中间N-1台，首尾各自算上半台，一共是N台

### 1.4.4 吞吐量

![image-20230917123931676](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230917123931676.png)

吞吐量就是接收速度，平均吞吐量就是平均接受速度。

![image-20230917124318285](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230917124318285.png)

![image-20230917124513194](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230917124513194.png)

![image-20230917124552792](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230917124552792.png)

考虑最慢的哪一个

![image-20230917124730752](C:\Users\15574\AppData\Roaming\Typora\typora-user-images\image-20230917124730752.png)

大家公用（平分）中间的大管子，如果中间的大管子不够粗的话，平分之后可能比接入网络还要细，成为整个系统的制约因素。

