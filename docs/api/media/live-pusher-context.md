### uni.createLivePusherContext(livePusherId, this)
创建 live-pusher 上下文 livePusherContext 对象。

**平台差异说明**

|App|H5|微信小程序|支付宝小程序|百度小程序|头条小程序|
|:-:|:-:|:-:|:-:|:-:|:-:|
|见下|x|√|x|x|x|


**参数说明**

设置live-pusher组件的推流地址，推流视频模式等。

属性|类型 |默认值|必填|说明
url|string| |是|推流地址，支持RTMP协议。
mode |string| |否|推流视频模式，可取值：SD（标清）, HD（高清）, FHD（超清）。
muted|Boolean|false|否|是否静音。
enable-camera|Boolean|true|否|开启摄像头。
auto-focus|Boolean|true|否|自动聚集。
beauty|Number|0|否|美颜，取值范围 0-9（iOS取值范围为1） ，0 表示关闭。
whiteness|Number|0|否|美白，取值范围 0-9（iOS取值范围为1） ，0 表示关闭。

**注意：**
- app-nvue 平台 2.2.5(alpha)+ 支持 uni.createLivePusherContext(livePusherId, this)
- app-nvue 平台 2.2.5(alpha)- 需要同时设置组件属性id和ref ``<live-pusher id="livepusher1" ref="livepusher1"></live-pusher>``，或者直接使用 ref，例如 ``this.$refs.livepusher1``


> 开始推流

##### callback 返回 Object 参数说明
属性|类型 |说明
type | String | "success" 表示成功， "fail" 表示失败

##### callback 返回 Object 参数说明

#### resume(callback)



#### stop(callback)


#### switchCamera(callback)


#### snapshot(callback)

#####  callback 返回 Object 参数说明
##### 成功时的回调
code|Number| 对应code码
message|object|{width:"快照图片宽度",height:"快照图片高度",tempImagePath:"快照图片路径"}。

##### 失败的回调
code|Number|
message|object|


#### startPreview(callback)


#### stopPreview(callback)


### 事件

> 状态变化事件
code|Number|
message|string|


> 网络状态通知事件
videoBitrate | 当前视频编/码器输出的比特率，单位 kbps
audioBitrate | 当前音频编/码器输出的比特率，单位 kbps
videoFPS | 当前视频帧率
videoGOP | 当前视频 GOP,也就是每两个关键帧(I帧)间隔时长，单位 s
netSpeed | 当前的发送/接收速度
netJitter | 网络抖动情况，抖动越大，网络越不稳定
videoWidth | 视频画面的宽度
videoHeight | 视频画面的高度

##### iOS 返回参数（detail）的详细说明
code|Number| code码
message|string| 具体的网络状态信息


errCode|Number|
errMsg|string|