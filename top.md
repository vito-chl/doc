### MODBUS Module

> modbus处理模块，包含rxana(接收分析模块)和txcea(发送生成模块)

#### rxana

> 分析总线传来的数据，命令 txcea 查询并发送数据或者向 SENSORCOMB 提供传感器设置信息

- bus_rx ：总线读取
- to_txcea ：发送给 txcea 的命令，当总线上请求数据时，告诉 txcea 取寻找数据并发送到总线上
- to_sensorcomb ：发送到 sensorcomb 的命令，当总线设置传感器时，将传感器ID和数据给到 sensorcomb 层

#### txcea

- req_sensorcomb ：当接到 rxana 解析出的的读取命令时从  sensorcomb 中请求数据
- from_rxana ： 接收来自 rxana 的命令
- bus_tx ：总线发送



### SENSORCOMB Module

> 传感器集合模块，接收 MODBUS Module 的消息并调用具体的协议联系传感器
>
> 保存传感器的配置信息，缓存传感器发送过来的数据

#### rxcomb

> 传感器接收汇总模块

- 

#### txcomb

> 传感器发送汇总模块

#### reg

> 传感器接收数据缓存，传感器发回数据时寄存下来

#### timerq

> 传感器配置模块，配置传感器的读取时间，并且会自动计时向传感器发送请求数据命令

#### 