## 电视家直播第三方服务器调用示例

### 步骤  
1.按照电视家指定的json文件格式，编辑频道列表  
2.将json文件保存在自己的服务器上。  
3.修改MainActivity.java中SERVER_URL为你自己的url。  
4.修改包名、签名为你自己期望的。  
5.编译、测试、发版。  

### 原理
电视家提供了自定义频道的播控等Intent接口。  

### API说明

#### 1.数字换台  
调用示例:  
> Intent intent = new Intent("com.elinkway.tvlive2.ChangeChannel"); Intent.putExtra("channel_num", "");  
> Intent.putExtra("from", "");  
> startService(intent);  

#### 2. 切换上一频道  
调用示例:  
> Intent intent = new Intent("com.elinkway.tvlive2.PreChannel"); Intent.putExtra("from", "");  
> startService(intent);  

#### 3. 切换下一频道  
调用示例:  
> Intent intent = new Intent("com.elinkway.tvlive2.NextChannel"); Intent.putExtra("from", "");  
> startService(intent);  

#### 4. 播放指定URL频道  
调用示例:  
> Intent intent = new Intent("com.elinkway.tvlive2.playUrl");  
> // 设置自定义频道列表地址  
> intent.putExtra("data_source", "http://7xo8iy.com2.z0.glb.qiniucdn.com/3rd.json");  
> // 播放自定义频道列表中的指定频道  
> intent.putExtra("channel_url", "http://gslb.live.video123456.com/gslb?stream_id=cctv3HD_1300&tag=live&ext=m3u8&sign=live_tv");  
> intent.putExtra("from", "");  
> intent.setFlags(Intent.FLAG_ACTIVITY_NEW_TASK);  
> intent.setComponent(new ComponentName("com.elinkway.tvlive2", "com.elinkway.tvlive2.activity.ThirdLauncherSplashActivity"));  
> startActivity(intent);  


## 声明
本程序仅供爱好者研究使用，请勿直接使用文中的url发布新的apk。
程序内部的3rd.json文件路径随时可能会失效，此时你可以将代码中内置的3rd.json部署到自己的服务器上进行测试。

