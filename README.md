#  异常值检测
## 异常值
+ 异常数据是数据分布的常态，处于特定分布区域或范围之外的数据通常会被定义为异常。
+ 产生异常的原因有很多，例如业务运营操作（网站广告费用增加10倍，导致流量激增）、数据采集问题（数据缺失、不全、溢出、格式匹配错误等）、数据同步问题（异构数据库同步过程中的丢失等）等
+ 处理异常数据之前，要先辨别出到底哪些是真正的数据异常：
1. 伪异常：由于业务特定运营动作产生，其实是正常反应业务状态，而不是数据本身的异常规律。比如某电商公司的A产品正常情况下日销量为1000台左右，由于昨天举行促销活动导致总销量达到10000台，由于后端库存备货不足导致今日销量又下降到100台。在这种情况下，10000台和100台都正确反应了业务运营的结果，而非数据异常。
2. 真异常：并不是由于特定的业务动作引起的，而是客观地反映了数据本身分布异常的个案。
+ 以下情况不需要对异常值做处理
1. 正常反映业务运营结果
2. 异常检测，主要针对整体样本中的异常数据进行分析和挖掘以便找到其中的异常个案和规律，这种检测围绕异常值展开，因此不能做抛弃处理
3. 包容异常值的数据建模，有些模型对异常值不敏感，即使不处理也不会对模型本身造成负面影响，如决策树
## 异常值检测模型
+ 检测异常值的方法称为异常检测
+ 常用于客户异常识别、信用卡欺诈、贷款审批识别、药物变异识别、恶劣气象预测、网络入侵检测、流量作弊检测等
+ 检测模型
1. 单维数据：3-sigma原理以及它的一些变式，如Grubbs、T-Test等等
2. 高维数据：通常有2种解决办法，a.先降低至单维度，再使用单维度方法解决；b.在高维度数据上建立模型，然后判断是否存在异常，常用模型如One Class SVM等
+ 异常检测的结果能说明异常么？
   算法作出的异常检测只会给出信息列表，但列表中的异常检测结果并不一定就符合实际情况，需要业务介入做进一步的筛查和审核，即
   在大多数场景下，通过非监督方法实现的异常值的结果知识用来缩小排查范围，为业务的执行提供更加精准和高效的执行目标而已
## 项目
+ 判断酒店是否有刷单等非法获利行为
