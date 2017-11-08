### 获取外汇牌价历史记录  

* ### Branch Visualization  
  基于threads1.0  

* 目录结构  
  /Data 获取汇率数据，相关脚本  
  /Visualization 可视化程序  

* display_control.pl  
  从 ../Data 目录获取数据并展示，线条图  
  指定数据文件：`our $DB_File = "../Data/2017.perldb.bin";`  
  ![](./Visualization/snap02.png)  

* display_triangulation.pl  
  ![](./Visualization/snap01.png)  

* display_nearly.pl  
  展示最近N天的汇率曲线图，在线获取最新的数据。  
  日期设置：`our $from = DateTime->today()->add( days => -5 );`  

* BUG  
  2007年8月15日出现最小值为0.076的情况，原因：  
  ```perl
  '2007.08.15' => {
    '16:29:01' => ['7.57','7.51','7.6',undef,'759.21','759.21'],
  }
  ```
