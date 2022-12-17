# Minio客户端使用
> 其实对于对象存储来说，MinIO Console的功能还是不够用的，所以官方还提供了基于命令行的客户端MinIO Client(简称mc)，下面我们来讲讲它的使用方法。

## 常用命令

> 我们先来熟悉下mc的命令，这些命令和Linux中的命令有很多相似之处。

| 命令    | 作用                                          |
| ------- | --------------------------------------------- |
| ls      | 列出文件和文件夹                              |
| version | 输出版本信息                                  |
| mb      | 创建一个存储桶或一个文件夹                    |
| rb      | 删除一个存储桶或一个文件夹                    |
| cat     | 显示文件和对象内容                            |
| pipe    | 将一个STDIN重定向到一个对象或者文件或者STDOUT |
| share   | 生成用于共享的URL                             |
| cp      | 拷贝文件和对象                                |
| mirror  | 给存储桶和文件夹做镜像                        |
| find    | 基于参数查找文件                              |
| diff    | 对两个文件夹或者存储桶比较差异                |
| rm      | 删除文件和对象                                |
| events  | 管理对象通知                                  |
| watch   | 监听文件和对象的事件                          |
| policy  | 管理访问策略                                  |
| session | 为cp命令管理保存的会话                        |
| config  | 管理mc配置文件                                |
| update  | 检查软件更新                                  |

## 安装及配置

> 由于MinIO服务端中并没有自带客户端，所以我们需要安装并配置完客户端后才能使用，这里以Docker环境下的安装为例。

### 拉取镜像

```dockerfile
docker pull minio/mc:latest
```

### 运行容器

```dockerfile
docker run -it --entrypoint=/bin/sh minio/mc
```

### 参数配置

```dockerfile
mc config host add <ALIAS> <YOUR-S3-ENDPOINT> <YOUR-ACCESS-KEY> <YOUR-SECRET-KEY>
```

以上命令解析

- ALIAS：服务别名
- YOUR-S3-ENDPOINT：服务地址
- YOUR-ACCESS-KEY：管理员账号
- YOUR-SECRET-KEY：管理员秘钥

## 命令实战

