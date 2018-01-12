# git-shell
shell for git, which convenient to use.

一、简介
该小脚本主要是能够部分配置操作的文件，而不需要手动去复制文件的路径（前提是操作的文件是修改过的文件），这样避免频繁去点鼠标（复制文件路径）。

二、各命令的使用

1. gi-co --> git checkout
- 功能
1. 文件路径部分匹配
2. 备份checkout后的文件
- 使用方法
gi-co [-r/d...] [fileNamelist]...

      -r retain 保留参数列表的文件，checkout其git st 的文件
      -d delete checkout 参数列表的文件
      -a checkout所有修改过的文件
     tips: 能够模糊搜索，fileNamelist 只需要做文件路径中的一个单词即可
     如：aps/customer/customer_dir/tcl/customer_tcl.h
     gi-co -d tcl
    checkout 的文件都备份在../checkout_Temp/temp-files
	
2. gi-add --> git add
- 功能
1. 文件路径部分匹配
- 使用方法
gi-co  [-a/r...]   [fileNamelist]...
        -r   retain 保留参数列表的文件，commit其git st 的文件
        -a  add 参数列表的文件
        -u  与git add -u 功能一样
        tips: 能够模糊搜索，fileNamelist 只需要做文件路径中的一个单词即可
        如：aps/customer/customer_dir/tcl/customer_tcl.h
        gi-co  -a  tcl
		
3. gi-df --> git diff
- 功能
1. 文件路径部分匹配
2. 任意文件组合查看diff
- 使用方法
gi-df [-r/d...] [fileNamelist]...

    -r  retain  保留参数列表的文件，git diff其git st 的文件
    -t  target  git diff 参数列表的文件
    -a/无参数  与git diff功能一样
    -c  cache   diff已经add在缓冲里的文件
    -s  stat 与git diff --stat一样
    tips: 能够模糊搜索，fileNamelist 只需要做文件路径中的一个单词即可
    如：aps/customer/customer_dir/tcl/customer_tcl.h
    gi-df -t tcl
4. gi-preset-commit

- 功能
每次提交都要写what why how，这个小工具可以替你避免这种重复的操作。
   提前给你预设好：
[bugfix/feature/config][][]
[what]
[why]
[how]

只需执行一次

三、结束
- tips：可以把这些文件copy到一个文件夹下如（~/git_tools), 然后export PATH=~/git_tools:$PATH，即可使用。把命令export PATH=~/git_tools:$PATH加到.bashrc中，就可以永久使用。
- 小脚本还在持续完善中
