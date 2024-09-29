```
根据当前类生成mysql的SQL语句，要求如下：
1、表名前缀为kunying_web
2、每个字段都是not null并且根据字段类型设置默认值，数值默认值为0，字符串默认值为''
3、create_dept、company_id、tenant_id、is_deleted、create_time、update_time、create_user、update_user为默认字段，不管模型中是否有该字段，sql都需要添加，并且按照示例的顺序放在最后。
4、请根据每个字段的注释含义，综合考虑后决定字段精度。

一个完整的表示例如下：
create table `kunying_web_scope_api`
(
    `id`            bigint auto_increment comment '主键'
        primary key,
    `scope_name`    varchar(64) not null default '' comment '接口权限名',
    `scope_path`    varchar(128) not null default '' comment '接口权限地址',
    `create_dept`     bigint(20) NOT NULL DEFAULT '-1' COMMENT '部门id',
    `company_id`     bigint(20) DEFAULT '-1' COMMENT '公司id',
    `tenant_id`     varchar(8) NOT NULL DEFAULT '00000000' COMMENT '租户id',
    `is_deleted`     tinyint(3) unsigned NOT NULL DEFAULT '0' COMMENT '删除标识-0未删除/1已删除',
    `create_time`     datetime NOT NULL DEFAULT CURRENT_TIMESTAMP COMMENT '创建时间',
    `update_time`     datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP COMMENT '最后更新时间',
    `create_user`     bigint(20) NOT NULL DEFAULT '-1' COMMENT '创建人id',
    `update_user`     bigint(20) NOT NULL DEFAULT '-1' COMMENT '修改人id'
) comment 'api鉴权' charset = utf8mb4;
```
