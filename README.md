# flink-connector-jdbc_extra_2.12
flink-connector-jdbc 增加了phoenix 的支持
 

###  用法说明
```xml
   CREATE TABLE base_dic ( 
        dic_code STRING, 
        dic_name STRING, 
        PRIMARY KEY (dic_code) NOT ENFORCED 
  ) WITH ( 
     'connector' = 'jdbc' ,
     'url' = 'jdbc:phoenix:hadoop102:2181', 
     'table-name' = 'GMALL2022.DIM_BASE_DIC'
   ) ;
 ```
 ###  注意
  如果有SCHEMA要放在表名前缀，库名表名都要大写。
 
  想要查看修改的地方 可以搜索 FIXED FOR PHOENIX 
 
 ### 使用是要引入phoenix驱动 

```xml
         <dependency>
            <groupId>org.apache.phoenix</groupId>
            <artifactId>phoenix-spark</artifactId>
            <version>5.0.0-HBase-2.0</version>
            <exclusions>
                <exclusion>
                    <groupId>org.glassfish</groupId>
                    <artifactId>javax.el</artifactId>
                </exclusion>
            </exclusions>
        </dependency>
```
