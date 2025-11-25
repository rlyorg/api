
# 良友电台开放平台

方便开发者利用良友电台的节目开发多样应用。

请先申请成为良友电台开发者（ https://open.729ly.net ），在调用API时传递 Bearer token 以标识来源，当然你也可以匿名方式调用。

```
'Authorization: Bearer evPSCZh0WtWJOlefBWbMotTegOgQJudmqAhhcoUH'
```



## API 参考

#### 获取所有节目列表

```http
  GET https://open.729ly.net/api/programs
```

| Header | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `Authorization` | `string` | **Optional**. Your Bearer Token |

#### 结果截图

![image.png](https://i.loli.net/2021/06/11/nTxRXm6CIkHlU8i.png)



#### 按分类获取节目元数据（分类中包含其分类下的节目信息）

```http
  GET https://open.729ly.net/api/categories
```

| Header | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `Authorization` | `string` | **Optional**. Your Bearer Token |

![image.png](https://i.loli.net/2021/06/11/9daEWPbxs8V17ek.png)



#### 获取当天节目列表

```http
  GET https://open.729ly.net/api/today
```

| Header | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `Authorization` | `string` | **Optional**. Your Bearer Token |

![image.png](https://i.loli.net/2021/06/11/kZlI5fgTiy6GdFM.png)



#### 按节目分类获取节目列表

```http
  GET https://open.729ly.net/api/program/{id}
```


| Header          | Type     | Description                     |
| :-------------- | :------- | :------------------------------ |
| `Authorization` | `string` | **Optional**. Your Bearer Token |

| Parameter | Type     | Description   |
| :-------- | :------- | :------------ |
| `id`      | `string` | **Required**. |

```Result
  结果格式同 “获取当天节目列表”，数量为365天内的节目（但下面良友圣经学院的5个节目为30天内的节目）
```

##### 结果字段play_at说明

play_at 为节目播放日期，请特别留意，良友圣经学院的5个节目，其含义为某科目的编号。

5个特殊类节目：

- /api/program/ltsnp
- /api/program/ltstpa1
- /api/program/ltstpa2
- /api/program/ltstpb1
- /api/program/ltstpb2
