Linux 一般是做服务端的操作系统。

# 常用的 linux 命令

## 1、常用命令

**1、ls（list）**：列举当前工作目录的内容

![image-20210411155038502](https://github.com/yanfengneng/study_node/blob/master/image/ls.png)

***



**2、pwd（print working directory）**：显示当前工作目录

![image-20210411155907349](https://github.com/yanfengneng/study_node/blob/master/image/pwd.png)

***



**3、cd（change directory）**：切换文件路径，cd 将给定的文件夹（或目录）设置成当前的工作目录

![image-20210411190700169](https://github.com/yanfengneng/study_node/blob/master/image/cd.png)

**cd ..**：打开上一级目录

**cd -**：用于本目录与上一个目录来回切换

**cd ~**：返回主目录

***

**4、mkdir（make diretory）**：用于新建一个新目录

![image-20210411210136029](https://github.com/yanfengneng/study_node/blob/master/image/mkdir.png)

***

**5、rm（remove）**：删除

**rm -d [目录名]**：删除给定目录

**rm -r [文件夹]**：删除给定文件夹

**rm [文件名]**：删除给定的文件

![image-20210411210418052](https://github.com/yanfengneng/study_node/blob/master/image/rm.png)

***

**6、mv（move）**：mv 命令对文件或文件夹进行移动，如果文件或文件夹存在于当前工作目录中，还可以对文件或文件夹进行重名名。

==mv [被移动的文件名|被移动的文件夹] [目标文件夹]==

![image-20210412110453987](https://github.com/yanfengneng/study_node/blob/master/image/mv.png)

***

**7、cp（copy）**：对文件进行复制

==cp [被复制的文件名] [新的文件名]==

***

**8、man rm**：查看所有手册

![image-20210412215610884](https://github.com/yanfengneng/study_node/blob/master/image/man%20rm.png)

**rm --help**：查看 rm 的所有命令

***

**9、which**：查看命令所在位置

例：**which ls**

![image-20210412223435850](https://github.com/yanfengneng/study_node/blob/master/image/which%20ls.png)

**which cd 为空，因为 cd 为 shell 内置的命令**

![image-20210412224144784](https://github.com/yanfengneng/study_node/blob/master/image/用户.png)

***

**10、touch**：创建文件命令

![image-20210413162842479](https://github.com/yanfengneng/study_node/blob/master/image/touch.png)

undatedb 需要在 sudo（管理员权限）下才能使用

***

**11、cat（concatenate and print files）**：用于在标准输出（监控器或屏幕）上查看文件内容

![image-20210413165213506](https://github.com/yanfengneng/study_node/blob/master/image/cat%20more.png)

***

**12、echo [变量]**：在显示器上显示一段文字，一般起到一个提示的作用。

**echo [字符串] > 文件名**：`>`是将该字符串`覆盖`到该文件中

**echo [字符串] >> 文件名**：`>>`是将字符串`追加`到该文件中

## 2、文件搜索

![image-20210413141846861](https://github.com/yanfengneng/study_node/blob/master/image/find.png)

![image-20210413143555333](https://github.com/yanfengneng/study_node/blob/master/image/find%20123.png)



**find：**搜索指定的文件

**find /home [-name|-iname] [文件名]**：-name 表示`区分大小写`的搜索，-iname 表示`不区分大小写`的搜索

![image-20210413145041350](https://github.com/yanfengneng/study_node/blob/master/image/-iname%20-name.png)

==通配符搜索的话，* 表示多个任意字符，？表示一个任意字符。==

***

**find /home/yfn/桌面 -size+1**：搜索桌面上文件大小大于512字节的文件（==+1 1 表示文件要大于512字节，因为一个数据块为512个字节==）

***

**grep [搜索内容] [文件名]**：在给定文件中搜寻指定的字符串。`grep -i `在搜寻时会忽略字符串的大小写，而`grep -r`则会在当前目录的文件中递归搜寻指定的字符串。

![image-20210413170844305](https://github.com/yanfengneng/study_node/blob/master/image/grep.png) 



**grep -v [搜索内容] [文件名]**：反向搜索，搜索不含有`[搜索内容]`的行

![image-20210413171104510](https://github.com/yanfengneng/study_node/blob/master/image/grep%20-v.png)



## 3、linux 用户管理

Linux 是多用户的操作系统

1、添加用户：`sudo useradd user1`

2、设置密码：`sudo passwd user1`

关于 sudo 命令：

==是允许系统管理员让普通用户执行一些或者全部的 root 命令的一个工具==，如 useradd、halt、reboot、su 等等，这样不仅减少了 root 用户的登录和管理时间，同样也提高了安全性。

***

用户组：

==每个用户都有一个初始组，可以有0个或多个附加组，是为了方便权限控制的。==

当创建用户的时候，系统会创建一个跟用户名同组的组。文件属性包括所属用户、所属用户组。

***

su：用于切换用户的。

userdel [用户名]：删除用户

![image-20210416152230717](https://github.com/yanfengneng/study_node/blob/master/image/userdel.png)

***

用户组的管理：

添加用户组：`groupadd group1`

![image-20210416153554500](https://github.com/yanfengneng/study_node/blob/master/image/groupadd.png)

给用户组改名：`groupmod -n group1new group1`

***

shell：是用来解析命令的，它用于接收用户命令，然后调用相应的程序执行。shell 相等于一个翻译，翻译我们的命令，让机器听懂。



