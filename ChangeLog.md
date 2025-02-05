#蓝莺IM Android版更新日志
[蓝莺IM](https://www.lanyingim.com/)，是由美信拓扑团队研发的新一代即时通讯云服务，SDK设计简单集成方便，服务采用云原生技术和多云架构，私有云也可按月付费。

## v3.3.2 - 2022/07/20

变更:
1. floo更新  版本 v3.3.2
2. 纠正API命名错误。

## v3.1.3 - 2022/07/09

变更:
1. floo更新  版本 v3.3.1

新增:
1. 国际化。支持英语和中文切换。
2. 修改产品名称为蓝莺IM。

## v3.0.8 - 2022/03/19

变更:
1. floo更新  版本 v3.1.23
2. 将app数据目录迁移到外部存储

## v3.0.7 - 2022/01/03

变更:
1. floo更新  版本 v3.1.23
2. Bug-fix:修改App ID

## v3.0.6 - 2021/11/01

变更:
1. floo更新  版本 v3.1.4
2. 分页获取群成员列表
3. 展示推送通知
4. 增加群内全员禁言功能

## v3.0.5 - 2021/08/08

变更:
1. floo更新  版本 v3.1.3

## v3.0.4 - 2021/06/24

新增:
1.  创建群聊可配置是否是聊天室

## v2.3.1 - 2020/05/27

变更:
1. 新的floo包 增加bugly符号表
2. 新增bugly符号表配置
3. onUserSignOut 增加userId参数
4. 登陆页可进入查看日志页面

## v2.3.0 - 2020/04/25

变更:
1. 新的floo包
   修改获取ChatManager UserManager RosterManager GroupManager的方式
   
## v2.2.1 - 2020/04/07

变更：
1. 网络请求超时时间更改为20s  

## v2.2.0 - 2020/03/27

变更：
1. 将同步接口更换成异步方式，可以直接在回调做相关业务处理
2. 增加BMXDataCallBack<T> BMXCallBack两种回调低缓BMXErrorCode返回
    
    ```
    /**
     * 获取所有会话
     **/
    - public void getAllConversations(BMXDataCallBack<BMXConversationList> callBack) {
        mService.getAllConversations(callBack);
    }
	```
	
	```
	 /**
     * 设置昵称
     **/
    - public void setNickname(String nickname, BMXCallBack callBack) {
        mService.setNickname(nickname, callBack);
    }

	```


## v2.1.0 - 2020/03/17

新增:
1. 会话：新增更新会话中消息的扩展字段接口

	```
	/// 更新一条数据库存储消息的扩展字段信息
	/// @param message 需要更改扩展信息的消息此时msg部分已经更新扩展字椴信息
	- updateMessageExtension:(BMXMessage msg);
	```

2. 命令消息：新增创建命令消息的接口
	
	```
	/// 创建发送命令消息(命令消息通过content字段或者extension字段存放命令信息)
	/// @param type 单群类型
	/// @param from 消息发送者
	/// @param to 消息接收者
	/// @param mtype 消息类型
	/// @param content 消息内容
	- public void sendCommandMessage(BMXMessage.MessageType type, long from, long to,
            String content)
	```

3.  新增收到命令消息通知接口

	```
	/**
	 * 收到命令消息
	 **/
	- public void onReceiveCommandMessages(BMXMessageList list) {}
	```
 



