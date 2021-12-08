# RollToolsApi

### 大道至简系列
[需求解决系列之-【系列工具概览】](https://juejin.im/post/5ed6174f51882542fb06d850)
此系列是大道至简的起始，将一系列简单恶心的操作封装起来，框架么，可以败絮其中，但一定要金絮其外！

一个提供开发中常用数据的一个稳定聚合Api接口源，运行于独立服务器，截止目前此服务已持续运行超过一年，服务器配置升级14次以上。免费，且长期维护，会持续添加新的接口！

如果在使用过程中有什么问题，或者有什么好的意见或者建议，都可以与我联系，mxnzp_life@163.com，或者扫描下方微信二维码添加我为好友，联系我请注明您的来意！

**主页地址：[ROLL](https://www.mxnzp.com)，目前接口已经支持https请求，推荐使用 https://www.mxnzp.com ，更安全，http://www.mxnzp.com 可继续使用，域名已经成功备案**

## 解锁新方式

### **郑重说明：非app_id请求方式将于2020年4月1日停止对外服务，请替换成app_id请求的方式，否则将无法正常使用接口！届时将拦截所有非app_id的请求**，对您的使用造成影响，敬请谅解！

**想体验接口？** 可获取临时app_id测试，获取方式：扫描下方小程序码->选择TAB-我的->点击获取临时app_id即可获取临时体验接口的app_id和app_secret，此app_id仅为测试使用，次日凌晨自动重置，重置之后之前生成的app_id将失效，真正使用接口请申请属于自己专属的app_id。

+ **各位开发者，为了更方便的使用，经过一段时间的努力，开通了app_id和app_secret方式请求接口的方式，使用此方式最大的好处在于不会再有使用上的限制，包括你可以在你的服务器中调用，包括不会限制你的调用频率，包括不会封IP！**
+ **如何注册app_id和app_secret呢？扫描下方小程序码（或者搜索小程序【Roll地盘】），进入我的页面，绑定手机号之后即可获取你的专属app_id和app_secret，使用新方式吧骚年！**
+ **如何确定是否正确使用了app_id的方式呢？**
  + 扫描下方小程序码（或者搜索小程序【Roll地盘】），进入我的页面，点击数据统计，这里将会显示接口的调用情况，如果配置正确，这里将会有统计数据。
+ **如何使用呢？**
  + 在每个请求链接后面添加app_id=你的app_id&app_secret=你的app_secret两个参数，如果是POST请求，需要将两个参数放在参数列表中请求
  + 【推荐方案】在请求头header中添加app_id=你的app_id&app_secret=你的app_secre两个参数，更加方便

<div style="background:#e3e3e3; color:#FFF" align=center ><img width="400" height="400" src="./png/xcx.jpg"/></div>

## 特别声明

**最近问的一个比较多的问题就是，接口访问404，在这里我想说，请各位大佬仔细阅读文档，仔细阅读文档，仔细阅读文档，尤其是"通用"模块的文档，我们的Host地址是域名+/api（https://www.mxnzp.com/api），不是纯域名，不要再来问题这个问题了。。。一个正常的请求应该是 https://www.mxnzp.com/api/xxxxx**

随着使用本api用户的增多，每一次对服务器的升级维护，都需要格外小心，否则将会影响到用户的使用。特此创建了一个交流群，**旨在交流使用通用接口中遇到的问题，以及其他新接口的建议，群中大佬云集，可以进行学术交流！有新接口的诞生也方便通知大家！另外一个作用就是，如果接口需要停机维护，会提前在群中通知，以免对大家的使用带来不便以及损失！**

前期开放扫描二维码进群的方式让群里多了很多发布淫秽，色情，赌博的广告信息，现关闭此方式，需要加群的请添加我微信好友，我拉你入群（备注下通用API），感谢您的支持！

**自助IP解封：对于使用中逻辑不正确导致的IP封禁，现提供自助解封方式，微信公众号搜索《Cretin的开发之路》，回复任意消息可召唤出自助服务系统，按照说明进行IP自助解封！如图三**

<div style="background:#e3e3e3; color:#FFF" align=center ><img width="200" height="300" src="./png/me.jpeg"/><img width="150" height="300" src="./png/gongzhonghao.jpg"/></div>

------

## 目录

- [通用](#通用)
- [更新记录](#更新记录)
- [捐赠](#捐赠)
- [版权声明](#版权声明)
- [接口列表，新接口将不会在此更新~](#接口列表)
  - [一、通用彩票信息接口](#一通用彩票信息接口)
    - [<strong>指定期号通用中奖号码</strong>](#指定期号通用中奖号码)
    - [<strong>最新通用中奖号码信息</strong>](#最新通用中奖号码信息)
    - [<strong>最近历史开奖数据</strong>](#最近历史开奖数据)
    - [<strong>获取彩种信息</strong>](#获取彩种信息)
    - [<strong>中奖结果计算</strong>](#中奖结果计算)
  - [二、节假日及万年历](#二节假日及万年历)
    - [<strong>指定日期的节假日及万年历信息</strong>](#指定日期的节假日及万年历信息)
    - [<strong>指定多个日期的节假日及万年历信息</strong>](#指定多个日期的节假日及万年历信息)
    - [<strong>指定月份所有的节假日及万年历信息</strong>](#指定月份所有的节假日及万年历信息)
    - [<strong>指定月份指定类型的所有的节假日及万年历信息</strong>](#指定月份指定类型的所有的节假日及万年历信息)
    - [<strong>指定年份所有的节假日及万年历信息</strong>](#指定年份所有的节假日及万年历信息)
    - [<strong>指定年份指定类型的所有的节假日及万年历信息</strong>](#指定年份指定类型的所有的节假日及万年历信息)
    - [<strong>获取最近节日信息</strong>](#获取最近节日信息)
  - [三、全国城市列表（全国地级市API，数据来源国家统计局），世界城市列表](#三全国城市列表全国地级市api数据来源国家统计局，世界城市列表)
    - [<strong>全国城市列表</strong>](#全国城市列表)
    - [<strong>搜索全国城市列表</strong>](#搜索全国城市列表)
    - [<strong>世界级国家城市列表</strong>](#世界级国家城市列表)
  - [四、IP地址信息](#四ip地址信息)
    - [<strong>获取访问者的ip地址信息</strong>](#获取访问者的ip地址信息)
    - [<strong>获取指定ip的ip地址信息</strong>](#获取指定ip的ip地址信息)
  - [五、小工具](#五小工具)
    - [<strong>获取不重复长ID</strong>](#获取不重复长id)
    - [<strong>获取不重复短ID</strong>](#获取不重复短id)
    - [<strong>获取服务器时间</strong>](#获取服务器时间)
  - [六、天气信息](#六天气信息)
    - [<strong>获取特定城市今日天气</strong>](#获取特定城市今日天气)
    - [<strong>获取特定城市今天及未来天气</strong>](#获取特定城市今天及未来天气)
  - [七、笑话段子](#七笑话段子)
    - [<strong>分页获取笑话段子列表</strong>](#分页获取笑话段子列表)
    - [<strong>随机获取笑话段子列表</strong>](#随机获取笑话段子列表)
  - [八、生成二维码](#八生成二维码)
    - [<strong>生成单一二维码</strong>](#生成单一二维码)
    - [<strong>生成带logo二维码</strong>](#生成带logo二维码)
  - [九、条形码相关](#九条形码相关)
    - [<strong>生成指定条形码</strong>](#生成指定条形码)
    - [<strong>获取条形码对应的商品信息</strong>](#获取条形码对应的商品信息)
  - [十、生成随机图片验证码](#十生成随机图片验证码)
    - [<strong>生成随机图片验证码</strong>](#生成随机图片验证码)
  - [十一、世界电话区号列表](#十一世界电话区号列表)
    - [<strong>世界电话区号列表</strong>](#世界电话区号列表)
  - [十二、音乐相关接口](#十二音乐相关接口)
    - [<strong>获取每日音乐推荐列表</strong>](#获取每日音乐推荐列表)
    - [<strong>获取榜单列表</strong>](#获取榜单列表)
    - [<strong>获取指定榜单的歌曲列表</strong>](#获取指定榜单的歌曲列表)
    - [<strong>搜索歌曲</strong>](#搜索歌曲)
    - [<strong>获取歌曲详情</strong>](#获取歌曲详情)
    - [<strong>搜索歌手</strong>](#搜索歌手)
    - [<strong>获取歌手详情</strong>](#获取歌手详情)
    - [<strong>获取歌手所有的歌曲列表</strong>](#获取歌手所有的歌曲列表)
  - [十三、手机号码归属地](#十三手机号码归属地)
    - [<strong>手机号码归属地查询</strong>](#手机号码归属地查询)
  - [十四、在线自定义参数](#十四在线自定义参数)
    - [<strong>创建一个应用</strong>](#创建一个应用)
    - [<strong>获取用户创建的应用列表</strong>](#获取用户创建的应用列表)
    - [<strong>给指定应用设置在线参数</strong>](#给指定应用设置在线参数)
    - [<strong>获取指定应用的在线参数</strong>](#获取指定应用的在线参数)
  - [十五、免费最新新闻](#十五免费最新新闻)
    - [<strong>获取所有新闻类型列表</strong>](#获取所有新闻类型列表)
    - [<strong>根据新闻类型获取新闻列表</strong>](#根据新闻类型获取新闻列表)
    - [<strong>根据新闻id获取新闻详情</strong>](#根据新闻id获取新闻详情)
  - [十六、垃圾分类](#十六垃圾分类)
    - [<strong>查询垃圾分类信息</strong>](#查询垃圾分类信息)
  - [十七、福利养眼图片](#十七福利养眼图片)
    - [<strong>随机获取福利图片</strong>](#随机获取福利图片)
    - [<strong>获取福利图片列表</strong>](#获取福利图片列表)
  - [十八、物流查询](#十八物流查询)
    - [<strong>查询支持的所有快递公司编号列表</strong>](#查询支持的所有快递公司编号列表)
    - [<strong>根据公司名称查询对应的公司编号</strong>](#根据公司名称查询对应的公司编号)
    - [<strong>根据快递单号识别出所属快递公司编号</strong>](#根据快递单号识别出所属快递公司编号)
    - [<strong>查询物流信息</strong>](#查询物流信息)
  - [十九、历史上的今天](#十九历史上的今天)
    - [<strong>获取历史上的今天数据</strong>](#获取历史上的今天数据)
  - [二十、简繁转换](#二十简繁转换)
    - [<strong>简体与繁体的转换</strong>](#简体与繁体的转换)
  - [二十一、文本翻译](#二十一文本翻译)
    - [<strong>文本翻译</strong>](#文本翻译)
  - [二十二、汉字字典](#二十二汉字字典)
    - [<strong>查询单个汉字的读音和含义</strong>](#查询单个汉字的读音和含义)
  - [二十三、每日精美语句](#二十三每日精美语句)
    - [<strong>每日推荐精美语句</strong>](#每日推荐精美语句)
  - 未完待续
  - [附件](#附件)
    - [<strong>天气描述清单</strong>](#天气描述清单)
    - [<strong>风力表清单</strong>](#风力表清单)
    - [<strong>风向表清单</strong>](#风向表清单)

------

## 通用

- **HOST地址：** **推荐使用https接口更安全：https://www.mxnzp.com/api** 之前的 **http://www.mxnzp.com/api** 可继续使用不受影响！

- **app_id和app_secret方式请求（摆脱被封IP的限制，可在服务器中调用接口）：** 

  - 在参数中添加app_id=你的app_id&app_secret=你的app_secret
  - 【推荐方案】在请求头header中添加app_id=你的app_id&app_secret=你的app_secret
  - 唯一获取app_id和app_secret方式，扫描上方小程序码进行操作！

- **说明：** 所有的接口都会返回如下格式的数据，具体数据包装在data中，需要根据状态来确定请求是否成功。

- **请求方法：** 所有的请求中都是大部分都是GET请求（如果有特殊情况，则会特殊标明）

- **数据返回格式：**

  ```java
  {
      "code": 1,
      "msg": "数据返回成功",
      "data": null
  }
  ```

- **数据返回格式说明（下面所有接口中的数据返回都是基于data的，不再介绍code和msg，请知悉）：**

  - **code：** 状态码 1 返回成功 0 返回失败 此时，请关注msg错误信息
  - **msg：** 提示信息，当code返回0的时候包含错误提示信息
  - **data：** 主要信息，不同接口返回的东西不一样

- **列表数据格式说明（大部分列表数据都满足下列格式，特殊接口除外，在此特别说明，后面就不再赘述了）**

  - **page：** 当前页数
  - **totalCount：** 总数量
  - **totalPage：** 总页数
  - **limit：** 每页数量
  - **list：** 每页具体数据
    - **具体列表数据模型**

------

## 更新记录

**2021-12-07 23:47:22**

+ 新增查询食物热量接口， [食物热量、卡路里查询](https://www.mxnzp.com/doc/detail?id=32)

**2021-11-11 19:57:01**

+ 新增抖音视频解析接口，可去水印 [抖音视频解析下载](https://www.mxnzp.com/doc/detail?id=31)

**2021-11-09 17:23:23**

+ 新增哔哩哔哩视频解析接口 [Bilibili视频解析下载](https://www.mxnzp.com/doc/detail?id=30)

**2021-10-21 14:14:00**

+ 节假日及万年历相关接口新增ignoreHoliday字段 [节假日及万年历](https://www.mxnzp.com/doc/detail?id=1)

**2021-10-02 18:12:00**

+ 新增驾考题库接口 [驾考题库](https://www.mxnzp.com/doc/detail?id=29)

**2021-09-29 13:22:00**

+ 新增实时汇率接口 [身份证查询](https://www.mxnzp.com/doc/detail?id=28)

**2021-09-27 17:57:00**

+ 新增实时汇率接口 [实时汇率](https://www.mxnzp.com/doc/detail?id=27)

**2021-09-24 19:46:14**

+ 新增生成短链接口 [URL生成短链接](https://www.mxnzp.com/doc/detail?id=26)

**2020-06-08 16:36:29**

+ 节假日及万年历相关接口新增 **indexWorkDayOfMonth** 字段，此字段返回是当前月的第几个工作日，[二、节假日及万年历](#二节假日及万年历)
+ 天气接口新增天气描述，风力描述，风向描述清单，[附件](#附件)

**2020-02-26 21:47:39**

+ 新增每日推荐精美语句接口，[二十三、每日精美语句](#二十三每日精美语句)

**2020-01-17 14:53:43**

+ 新增汉字字典接口，[二十二、汉字字典](#二十二汉字字典)

**2020-01-16 22:16:09**

+ 新增翻译接口，[文本翻译](#文本翻译)

**2020-01-13 23:28:37** 

+ 新增简繁转换的接口，[简体与繁体的转换](#简体与繁体的转换)

**2019-11-20 10:12:34**

+ 新增app_id+app_secret 方式请求接口，使用此方式可避免请求限流以及封禁IP。[解锁新方式](#解锁新方式)
+ 新开发《Roll地盘》小程序，可以申请app_id+app_secret，可以查询你申请的app_id下每日请求统计数据！

**2019-09-09 09:44:35**

+ 新增获取历史上的今天的接口！[查看说明](#十九历史上的今天)

**2019-08-28 12:10:13**

+ 彩票通用接口新增：
  + 最近历史开奖数据！[查看说明](#最近历史开奖数据)
  + 彩种类型信息获取！[查看说明](#彩种类型信息获取)
  + 中奖结果计算！[查看说明](#中奖结果计算)

**2019-08-10 19:23:14**

+ 新增获取最近节日信息！[查看说明](#获取最近节日信息)

**2019-08-06 23:09:05**

- 新增其他彩种的彩票信息，包括之前的双色球一共七种彩种，聚合成一个接口方便调用，当然，之前的双色球接口使用已做兼容处理，不会受到影响！[查看说明](#一通用彩票信息接口)

**2019-07-24 23:54:27**

- 新增物流查询的接口，[查看说明](#十八物流查询)
- 段子接口当请求页数超过最大页数时返回空数组
- 修复一些已知的bug

**2019-07-10 20:22:17**

- 哦吼哦吼，新增福利图片接口，[查看说明](#十七福利养眼图片)

**2019-07-08 17:59:41**

- 新增垃圾分类信息查询接口，[查看说明](#十六垃圾分类)
- 修复线上一些已知bug

**2019-07-05 19:15:06**

- 新增获取不同类型最新新闻的接口，[查看说明](#十五免费最新新闻)

**2019年07月02日 19:30:22**

- 新增获取服务器时间的接口，[查看说明](#获取服务器时间)
- 新增在线自定义参数的接口，[查看说明](#十四、在线自定义参数)

**2019年06月05日15:54:50**

- 新增查询手机归属地的接口，[查看说明](#十三手机号码归属地)
- IP地址查询的接口逻辑优化，数据搜索更加准确，[查看说明](#四ip地址信息)
- 音乐搜索新增page参数，可实现数据分页查询，[查看说明](#搜索歌曲)

**2019年05月22日13:07:41**

- 新增音乐相关接口，拥有这些接口，基本上可以实现一个小的音乐播放器，[查看说明](#十二音乐相关接口)

**2019年05月15日11:57:20**

- 新增国家电话区号列表接口，[查看说明](#十一世界电话区号列表)
- 国家城市列表接口新增世界级国家城市列表查询，[查看说明](#世界级国家城市列表)

**2019年04月11日23:59:55** 

- 服务器已经支持https请求，之前的http请求不受影响！

**2019年03月13日11:27:58**

- 一、服务器硬件更新
  - 1、升级服务器内存和cpu
- 二、接口更新（本次没有新接口添加）
  - 1、节假日api的假日信息更新到2002年，2002年之前的节假日信息国务院没有发布，不再做统计！[查看说明](#二节假日及万年历)
  - 2、节假日api每日信息新增星座字段！[查看说明](#二节假日及万年历)
  - 3、修复天气api模糊搜索的bug，现在搜索会先全量匹配，匹配不到才会进行模糊匹配！[查看说明](#六天气信息)

**2019年01月29日09:53:10**

- 新增生成条形码接口，可以生成商品对应的条形码，[查看说明](#生成指定条形码)；新增条形码对应的商品信息，输入条形码上的商品code，可以获取对应的商品信息，[查看说明](#获取条形码对应的商品信息)。

**2019年01月09日20:16:38**

- 新增生成随机验证码的接口，可以生成任意长度的验证码图片，[查看说明](#十生成随机验证码)；段子接口新增随机段子列表，可以获取随机段子，[查看说明](#随机获取笑话段子列表)。

**2018年12月14日15:02:00**

- 新增生成二维码的接口，可生成指定大小，指定内容的二位么，也可生成带logo的二维码。[查看说明](#八生成二维码)

**2018年12月10日22:54:46**

- 节假日及万年历接口添加新的接口，添加查询指定类型的节假日信息列表，比如节日，休息日，工作日 [查看说明](#指定月份指定类型的所有的节假日及万年历信息) 和 [查看说明](#指定年份指定类型的所有的节假日及万年历信息)

**2018年12月07日09:20:07**

- 添加正式域名，可用正式域名访问 [查看说明](#通用)

**2018年12月01日22:49:42** 

- 新增笑话段子的api接口 [查看说明](#七笑话段子)

**2018年11月27日23:14:49**

- 新增天气查询的api接口 [查看说明](#六天气信息)

------

## 捐赠

由于服务器端的维护以及部分接口的维护都是需要付费的，所以如果此项目对您有帮助，还希望您捐赠支持，让我能好好的一直坚持下去。金额不在于多少，一份心意就好！在此感谢捐赠列表中所有的捐赠者，你们的鼓励是我最大的动力！[捐赠列表](https://www.mxnzp.com/website/page/donate)

<div style="background:#e3e3e3; color:#FFF" align=center ><img width="220" height="300" src="./png/wechat_small.jpeg"/>&nbsp;&nbsp;&nbsp;&nbsp;<img width="200" height="300" src="./png/alipay_small.jpeg"/></div>
---------

## 版权声明

本站所对外提供的Api接口中，部分数据来源于网络，如有侵权，请联系我进行处理！

本站所提供的所有Api接口仅仅是秉承交流学习的思想，没有任何盈利的行为，用户在使用过程中造成的版权问题由使用者自行承担，与本站维护者无关，请知悉！

-------

## 接口列表

由于当前项目仅仅是文档项目，有新接口时不方便更新，后续新接口将在个人主页更新，请知悉~

文档地址：https://www.mxnzp.com/doc/list

### **附件**

#### **天气描述清单**

+ 晴
+ 少云
+ 晴间多云            
+ 多云
+ 阴
+ 有风
+ 平静
+ 微风
+ 和风
+ 清风
+ 强风/劲风
+ 疾风
+ 大风
+ 烈风
+ 风暴
+ 狂爆风
+ 飓风
+ 热带风暴
+ 霾
+ 中度霾
+ 重度霾
+ 严重霾
+ 阵雨
+ 雷阵雨
+ 雷阵雨并伴有冰雹
+ 小雨
+ 中雨
+ 大雨
+ 暴雨
+ 大暴雨
+ 特大暴雨
+ 强阵雨
+ 强雷阵雨
+ 极端降雨
+ 毛毛雨/细雨
+ 雨
+ 小雨-中雨
+ 中雨-大雨
+ 大雨-暴雨
+ 暴雨-大暴雨
+ 大暴雨-特大暴雨
+ 雨雪天气
+ 雨夹雪
+ 阵雨夹雪
+ 冻雨
+ 雪
+ 阵雪
+ 小雪
+ 中雪
+ 大雪
+ 暴雪
+ 小雪-中雪
+ 中雪-大雪
+ 大雪-暴雪
+ 浮尘
+ 扬沙
+ 沙尘暴
+ 强沙尘暴
+ 龙卷风
+ 雾
+ 浓雾
+ 强浓雾
+ 轻雾
+ 大雾
+ 特强浓雾            
+ 热
+ 冷
+ 未知

#### **风力表清单**

+ ≤3
+ 4	
+ 5
+ 6	
+ 7
+ 8	
+ 9
+ 10	
+ 11
+ 12

#### **风向表清单**

+ 无风向
+ 东北
+ 东
+ 东南
+ 南
+ 西南
+ 西
+ 西北
+ 北
+ 旋转不定

