# 消费者人群画像——信用智能评分
## 排名
- A榜  12
- B榜  10

## 感想
第一次在DF上参加比赛，还是有很多遗憾，感觉很多潜力都没发挥出来，希望下次能做的更好。

## 赛题任务
  中国移动福建公司提供2018年x月份的样本数据（脱敏），包括客户的各类通信支出、欠费情况、出行情况、消费场所、社交、个人兴趣等丰富的多维度数据，参赛者通过分析建模，运用机器学习和深度学习算法，准确评估用户消费信用分值。
  
## 赛题来源
[DCIC 消费者信用评分](https://www.datafountain.cn/competitions/337/details/rule)
  
## 数据说明
本次提供数据主要包含用户几个方面信息：身份特征、消费能力、人脉关系、位置轨迹、应用行为偏好。字段说明如下：

|            字段列表            |                           字段说明                           |
| :----------------------------: | :----------------------------------------------------------: |
|            用户编码            |                         数值 唯一性                          |
|     用户实名制是否通过核实     |                          1为是0为否                          |
|            用户年龄            |                             数值                             |
|         是否大学生客户         |                          1为是0为否                          |
|         是否黑名单客户         |                          1为是0为否                          |
|        是否4G不健康客户        |                          1为是0为否                          |
|         用户网龄（月）         |                             数值                             |
| 用户最近一次缴费距今时长（月） |                             数值                             |
| 缴费用户最近一次缴费金额（元） |                             数值                             |
| 用户近6个月平均消费话费（元）  |                             数值                             |
|    用户账单当月总费用（元）    |                             数值                             |
|     用户当月账户余额（元）     |                             数值                             |
|    缴费用户当前是否欠费缴费    |                          1为是0为否                          |
|         用户话费敏感度         | 用户话费敏感度一级表示敏感等级最大。 根据极值计算法、叶指标权重后得出的结果，根据规则，生成敏感度用户的敏感级别： 先将敏感度用户按中间分值按降序进行排序，前5%的用户对应的敏感级别为一级： 接下来的15%的用户对应的敏感级别为二级； 接下来的15%的用户对应的敏感级别为三级； 接下来的25%的用户对应的敏感级别为四级； 最后40%的用户对应的敏感度级别为五级。 |
|       当月通话交往圈人数       |                             数值                             |
|       是否经常逛商场的人       |                          1为是0为否                          |
|    近三个月月均商场出现次数    |                             数值                             |
|    当月是否逛过福州仓山万达    |                          1为是0为否                          |
|   当月是否到过福州山姆会员店   |                          1为是0为否                          |
|         当月是否看电影         |                          1为是0为否                          |
|        当月是否景点游览        |                          1为是0为否                          |
|      当月是否体育场馆消费      |                          1为是0为否                          |
|     当月网购类应用使用次数     |                             数值                             |
|   当月物流快递类应用使用次数   |                             数值                             |
|  当月金融理财类应用使用总次数  |                             数值                             |
|   当月视频播放类应用使用次数   |                             数值                             |
|     当月飞机类应用使用次数     |                             数值                             |
|     当月火车类应用使用次数     |                             数值                             |
|   当月旅游资讯类应用使用次数   |                             数值                             |


## 作品要求
参赛者提交结果文件必须包含：id, score两列。
使用统一的标准csv格式，用英文半角","进行csv文件分割，文件使用UTF-8编码。
第1列为id列表示用户编码 。
第2列为score列表示信用分。信用分值应取整数。

## 评分方式
score = 1/(1+MAE)

## 文件说明
| 文件夹        | 文件           | 说明                                               |
| ------------- | -------------- | -------------------------------------------------- |
| experiment    | auto_ml.ipynb  | AutoML，A榜效果不好                                |
| -             | average.ipynb  | 3个模型平均，未做提交数据处理，线下417左右，过拟合 |
| -             | catboost.ipynb | CatBoost，A榜线上6379                              |
| -             | EDA.ipynb      | EDA                                                |
| -             | lgb_391.ipynb  | LGB，A榜线上6391，3套特征其中之一                  |
| -             | lgb_392.ipynb  | LGB，A榜线上6392，3套特征其中之一                  |
| -             | lgb_393.ipynb  | LGB，A榜线上6393，3套特征其中之一                  |
| -             | xgb.ipynb      | XGB，A榜线上3679                                   |
| map           | analysis.mmap  | 思维导图                                           |
| original_data | 数据           | 主办方提供的数据                                   |
| result        | result.md      | A榜结果说明                                        |


