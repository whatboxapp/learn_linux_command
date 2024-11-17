# Linux 基础指令教程：快速上手

## 1. 什么是 Linux 文件系统？

Linux 文件系统结构以 `/` 作为根目录，所有文件和目录都在其下层：

- `/home`：用户主目录，例如 `/home/boyue`
- `/etc`：系统配置文件目录
- `/var`：日志文件和动态数据存放目录

## 2. 目录相关指令

### 2.1 cd (Change Directory)

用于切换目录。

**使用：**


```bash
cd [目标目录]
```

**示例：**

切换到根目录：


```bash
cd /
```

切换到用户主目录：

```bash
cd ~
```

切换到上一级目录：


```bash
cd ..
```

切换到绝对路径 `/home/user`：


```bash
cd /home/user
```

切换到上一次所在目录：

```bash
cd -
``` 

切换到相对路径 `Documents`：


```bash
cd Documents
```

### 2.2 目录的概念

绝对路径： 从根目录 `/` 开始的路径，例如 `/home/user/Documents`。
相对路径： 相对于当前目录的路径，例如 Documents 或 ../Downloads。

### 2.3 查看当前路径：pwd

`Print Working Directory`，显示当前所在目录。

**使用**


```bash
pwd
```

**示例：**

显示当前路径：


```bash
pwd
```

输出：

```bash
/home/user
```

### 3. 查看目录内容：

```bash
ls
```

用于列出指定目录的内容。

**使用：**


```bash
ls [选项] [目录]
```

**常用选项：**

- `ls`：列出当前目录内容。
- `ls -l`：显示详细信息（权限、大小、时间等）。
- `ls -a`：显示隐藏文件（以.开头的文件）。
- `ls -h`：以可读格式显示文件大小。

**示例：**

查看当前目录内容：


```bash 
ls
```

查看目录详细信息：


```bash
ls -l
```

查看隐藏文件：


```bash
ls -a
```

### 4. 输出文本：echo

用于输出字符串或变量值。

**使用：**



```bash
echo [字符串或变量]
```

**示例：**

输出一个字符串：


```bash
echo "Hello, Linux!"
```

显示环境变量：


```bash
echo $HOME
```

### 5. 综合练习

打开终端，确认当前路径：


```bash
pwd
```

切换到 `/home` 目录，列出其中内容：


```bash
cd /home
ls
```

切换到用户主目录，创建一个测试目录：


```bash 
cd ~
mkdir test_directory
```

列出新建目录内容，并显示详细信息：


```bash
ls -l test_directory
```

输出一条信息：


```bash
echo "学习Linux指令很有趣！"
```

## 6. 总结

- `pwd`：查看当前所在路径。
- `cd`：切换目录（绝对路径或相对路径）。
- `ls`：查看目录内容（可加选项）。
- `echo`：输出文本或变量值。



## 扩展：ls 命令

下面是一些常用的 `ls` 命令选项：

- `-l`：以长格式显示文件和目录的详细信息，包括文件类型、权限、硬链接数、所有者、组、大小和修改时间。

```bash
ls -l
```

- `-a`：显示所有文件，包括以点（.）开头的隐藏文件。

```bash
ls -a
```

- `-h`：与 `-l`  结合使用时，显示文件大小时使用易读的格式（如 KB、MB、GB）。

```bash
ls -lh
```

- `-R`：递归列出所有子目录的内容。

```bash
ls -R
```

- `-t`：根据文件的修改时间排序，最新的文件排在前面。

```bash
ls -lt
```

- `-r`：反向排序，即将文件按相反的顺序排列。

```bash
ls -lr
```

- ` -S`：根据文件大小排序，最大的文件排在前面。

```bash
ls -lS
```

- `--color`：根据文件类型为输出的文件加上颜色，通常用于增强可读性。

```bash
ls --color=auto
```

- `-1`：每行列出一个文件。

```bash

ls -1
```

- `-d`：仅显示目录本身，而不列出目录中的文件。

```bash
ls -d */
-F：在文件名后加上符号，指示文件类型。例如，/ 表示目录，* 表示可执行文件。

```bash
ls -F
```

- `--group-directories-first`：优先显示目录，目录显示在文件之前。

```bash
ls --group-directories-first
```

- `-i`：显示文件的 inode 号码。

```bash
ls -i
```

- `-v`：按版本号顺序对文件进行排序（适用于文件名中包含数字的情况）。

```bash 
ls -v
```

### 组合叠加选项

你可以将多个选项组合使用，例如：

`ls -lha` 会列出当前目录下的所有文件（包括隐藏文件），并以长格式显示文件的详细信息，且文件大小会使用易读的格式（如 KB、MB）表示。

```bash
ls -lha
```

输出：

```bash
drwxr-xr-x  3 user user 4.0K Nov 16 10:20 .
drwxr-xr-x  4 user user 4.0K Nov 15 12:10 ..
-rw-r--r--  1 user user  1.5M Nov 16 09:45 file1.txt
-rw-r--r--  1 user user  256K Nov 14 16:30 .hidden_file
-rwxr-xr-x  1 user user  2.3M Nov 12 15:00 script.sh
```

会以长格式列出当前目录下的所有文件（包括隐藏文件），并按修改时间排序，最新修改的文件显示在最前面。
```bash
ls -atl
```

输出：

```bash
-rw-r--r--  1 user group  1024 Nov 16 10:20 .hidden_file
drwxr-xr-x  2 user group  4096 Nov 16 09:15 subdir
-rw-r--r--  1 user group  2048 Nov 15 14:05 regular_file
```




