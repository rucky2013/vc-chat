## pri_message
---
### Properties
Number|Name|Type|Length|Digit|NotNull|Default|Remark
  ---|---|---|---|---|---|---|---
1|	id|	Long|	19|	0|	Y|	null|	   
2|	send_id|	String|	64|	0|	Y|	null|	发件人id   
3|	rec_id|	String|	64|	0|	Y|	null|	收件人id   
4|	message|	String|	65535|	0|	N|	null|	消息内容   
5|	type|	Integer|	10|	0|	Y|	null|	0 普通消息 1 系统消息 2 点赞  3 关注 4 评论消息 5 作品 6 部落 7 签约 8 活动    
6|	created_time|	Date|	19|	0|	Y|	CURRENT_TIMESTAMP|	创建时间   
7|	dialogue_id|	Long|	19|	0|	Y|	null|	对话id   
8|	uni_id|	String|	32|	0|	N|	null|	   


### sql
```sql
CREATE TABLE IF NOT EXISTS `pri_message` (
  `id` bigint(20) NOT NULL AUTO_INCREMENT,
  `send_id` varchar(64) CHARACTER SET utf8 NOT NULL COMMENT '发件人id',
  `rec_id` varchar(64) CHARACTER SET utf8 NOT NULL COMMENT '收件人id',
  `message` text COMMENT '消息内容',
  `type` int(1) NOT NULL COMMENT '0 普通消息 1 系统消息 2 点赞  3 关注 4 评论消息 5 作品 6 部落 7 签约 8 活动 ',
  `created_time` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP COMMENT '创建时间',
  `dialogue_id` bigint(20) NOT NULL COMMENT '对话id',
  `uni_id` varchar(32) DEFAULT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `uni_id` (`uni_id`),
  KEY `dialougue_id` (`dialogue_id`),
  KEY `created_time` (`created_time`),
  KEY `type` (`type`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;



```
