# WeChat AirKiss
AirKiss终端协议实现

调用过程
1 airkiss_init
2 开始抓包，获取802.11数据长度以及bssid和source address
3 airkiss_input
4 airkiss_state获取状态，如果状态为AIRKISS_DONE跳转到5，判断超时，如果超时跳转到7，否则跳转到2
5 通过airkiss_pwd airkiss_ssid 获取WiFi设置，启用WiFi设备
6 等待网络启动，airkiss_answer 回应WeChat（最好回应多次），过程结束
7 切换WiFi通道，并airkiss_reset重设状态机，跳转到2

注：
上面提到的超时需要自己实现airkiss_input没有实现
