# v2ex_demo
写一个 [^V2ex 论坛]: www.v2ex.com 的演示版本



### 接口说明

按照官方提供的文档，接口仅提供了4个

* 最热10大主题

每日更新

地址：https://www.v2ex.com/api/topics/hot.json
方法：get
返回数组，每个对象对应一个主题

> node（name, url,id, avatar_mini,avatar_normal,avatar_normal）
> member（username, url,id,avatar_large,avatar_mini,avatar_normal）
> title
> url
> replies
> id



* 最新主题

首页全部这个tab下的最新内容
地址：https://www.v2ex.com/api/topics/latest.json
方法：get
返回数组，每个对象对应一条内容

> node(name,url,id,avatar_normal,avatar_normal)
> member（username, url,id,avatar_large,avatar_mini,avatar_normal）
> title
> url
> replies
> id



* 节点信息

查询对应节点的名字、间接，url，还有头像图片地址
地址：https://www.v2ex.com/api/nodes/show.json
方法：get，接收参数 name， name: 节点名（全是半角英文或数字）
例如： https://www.v2ex.com/api/nodes/show.json?name=js
无返回信息时：

> status: error
> message: Object Not Found
> rate_limit (默认情况下，每个 IP 每小时可以发起的 API 请求数被限制在 120 次)

有返回信息时：

> name, title, url, header, avatar_mini, avatar_normal, avatar_large, id



* 用户主页

获取用户信息，包括自我介绍，社交网站信息
地址：https://www.v2ex.com/api/members/show.json
方法：get, 接收参数 username,id 

> username
> bio
> url
> avatar_mini, avatar_normal, avatar_large
> id