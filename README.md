<!-- vscode-markdown-toc -->
* 1. [总体任务说明](#)
* 2. [How to do the assignments](#Howtodotheassignments)
	* 2.1. [视频教程](#-1)
	* 2.2. [文字教程](#-1)
* 3. [COS](#COS)
* 4. [环境配置](#-1)
	* 4.1. [本地配置](#-1)
	* 4.2. [虚拟机环境](#-1)
* 5. [Build书本](#Build)
* 6. [审核PR](#PR)
* 7. [Google Colab](#GoogleColab)
* 8. [个人小记(可忽略)](#-1)
	* 8.1. [添加远程仓库](#-1)
	* 8.2. [创建branch再提交](#branch)
	* 8.3. [回退commit](#commit)
	* 8.4. [同步本地仓库](#-1)
	* 8.5. [Branch操作](#Branch)
	* 8.6. [vscode快捷键](#vscode)
* 9. [如何找资料](#-1)
	* 9.1. [Kaggle](#Kaggle)
	* 9.2. [GitHub](#GitHub)
	* 9.3. [Visualization](#Visualization)

<!-- vscode-markdown-toc-config
	numbering=true
	autoSave=true
	/vscode-markdown-toc-config -->
<!-- /vscode-markdown-toc --># ocademy-how-to-ramp-up
##  1. <a name=''></a>总体任务说明
和同学们说明一下各位下一阶段的任务
1. 我们的主线目标是建成我们的[开源书](https://press.ocademy.cc/intro.html)
2. 小任务包括将他人开源仓库添加至我们的仓库，增加可视化内容，修复bug等
3. 请各位同学在[project](https://github.com/ocademy-ai/machine-learning/projects?query=is%3Aopen)里查看自己的任务，提交pr后进行关联（在pr右侧的development输入issue编号，更改状态）
4. 目前资源请全部放至COS云端
5. 关于github操作，请参考[陈伦德老师的视频](https://www.bilibili.com/video/BV1qv4y1R7L7/?spm_id_from=333.999.0.0)或者在网上寻找相关资源
6. 建书的相关流程请参考[contributing](https://github.com/ocademy-ai/machine-learning/blob/main/CONTRIBUTING.md)
7. 有问题随时在群内询问，不要卡在那里好久耽误整体任务进度

##  2. <a name='Howtodotheassignments'></a>How to do the assignments
我们将对[Ocademy仓库](https://github.com/ocademy-ai/machine-learning)(upstream)做出贡献，而在[Ocademy网站](https://press.ocademy.cc/intro.html)可以查看文件的渲染效果

[STYLE_GUIDE.md](https://github.com/ocademy-ai/machine-learning/blob/main/open-machine-learning-jupyter-book/STYLE_GUIDE.md)文件给出了构建书本的风格规范，如果任务中某文件在jupyter lab里渲染不成功，可以查阅该文件给出的格式规范

###  2.1. <a name='-1'></a>视频教程
[中文版](https://www.bilibili.com/video/BV1uW4y1s7Ci)和[英文版]( https://www.bilibili.com/video/BV1nM41167j9)教程自行选择观看

###  2.2. <a name='-1'></a>文字教程
首先需要fork一个自己的仓库(origin)，再创建一个新的分支，对该分支提交`commit`，最后从自己的仓库提交`Pull Request`到Ocademy仓库
![fork](images/fork.jpg)

关于Github Pull Request，参考Lunde老师[系列视频](https://space.bilibili.com/472463946/channel/collectiondetail?sid=917876)

>**notice**
>
>每次提交PR，不要直接从main分支提交，最好创建一个分支，从该分支提交
>
>It's better that you submit your PR from another branch than main.

##  3. <a name='COS'></a>COS
先下载[COSBrowser](https://cloud.tencent.com/document/product/436/11366),再查看[COS视频教程](https://netdisk-1300131294.cos.ap-shanghai.myqcloud.com/Tutorial-lunde-tencent-cos-storage.mp4)，`SecretId`和`SecretKey`请查看群公告，同时多关注群公告的注意事项

项目用到的dataset、css/js等文件都需要放在COS，许多教程视频也放在了COS，自主摸索查看这些视频

##  4. <a name='-1'></a>环境配置
###  4.1. <a name='-1'></a>本地配置
环境配置请参考[CONTRIBUTING.md](https://github.com/ocademy-ai/machine-learning/blob/main/open-machine-learning-jupyter-book/CONTRIBUTING.md),该文件也提供了常见error的解决，遇到问题多参考

推荐使用ssh克隆代码至本地(local): `git clone git@github.com:ocademy-ai/machine-learning.git`

如果你还没有配置ssh,参考以下方法将默认的git安装方式更改为ssh
>1. 打开终端或命令行工具，输入以下命令以检查您当前的git配置：
>  ```
>  git config --list
>  ```
>2. 如果您看到以下输出，请跳到第4步：
>  ```
>  user.name=Your Name
>  user.email=your.email@example.com
>   ```
>   否则，请继续执行以下步骤。
>
>3. 设置您的用户名和电子邮件地址：
>   ```
>  git config --global user.name "Your Name"
>  git config --global user.email "your.email@example.com"
>  ```
>4. 更改git的默认传输协议为ssh：
>   ```
>  git config --global url."git@github.com:".insteadOf "https://github.com/"
>   ```
>现在，您应该能够使用ssh协议从GitHub安装软件包了。

###  4.2. <a name='-1'></a>虚拟机环境
本地环境配不好可以使用虚拟机镜像，里面的环境已为我们配置好了，可以直接用来 build 我们的书，也可以直接访问 Google

配有[视频](https://netdisk-1300131294.cos.ap-shanghai.myqcloud.com/vwware/VMWare-VM-build-ready-video.mp4)，视频中的相关文件存放在COS中的`netdisk-1300131294/vwware`文件夹下

##  5. <a name='Build'></a>Build书本
四种build书本的方法，其中本地build书本没有提供视频教程，[虚拟机](https://netdisk-1300131294.cos.ap-shanghai.myqcloud.com/vwware/VMWare-VM-build-ready-video.mp4)、[Docker](https://netdisk-1300131294.cos.ap-shanghai.myqcloud.com/Ocademy/Tutorials/xusenbo-wsl2-docker-install-and-connect-to-vscode.mp4)和[Github Action](https://netdisk-1300131294.cos.ap-shanghai.myqcloud.com/Ocademy/Tutorials/lunde-use-github-actions-for-testing.mp4)提供了视频教程

##  6. <a name='PR'></a>审核PR
如何审核其他人的PR，参考Lunde老师的[review Assignments](https://netdisk-1300131294.cos.ap-shanghai.myqcloud.com/Ocademy/Tutorials/Lunde_Chen_How_to_review_Assignments.mp4)和[review JupyterBook](https://netdisk-1300131294.cos.ap-shanghai.myqcloud.com/Ocademy/Tutorials/Lunde_Chen_How_to_review_JupyterBook.mp4)这两个视频

##  7. <a name='GoogleColab'></a>Google Colab
[Google Colab](https://colab.research.google.com/)是一个免费的基于云端的Jupyter笔记本环境，为研究者提供一定免费的GPU，不需要什么设置与环境配置

我们现在的每个notebook都是可以单独运行的，因此在我们笔记本没有GPU的情况下可以利用Google Colab提供的免费GPU运行notebook

##  8. <a name='-1'></a>个人小记(可忽略)
###  8.1. <a name='-1'></a>添加远程仓库
`git remote add origin git@github.com:Nicole-ying/machine-learning.git` 自己的远程仓库命名为origin

`git remote add upstream git@github.com:ocademy-ai/machine-learning.git` ocademy仓库命名upstream

`git remote -v` 查看远程仓库地址

###  8.2. <a name='branch'></a>创建branch再提交
在本地仓库创建一个新的分支，在新的分支上进行操作，再push到远程仓库

`git checkout -b branchname` 创建本地仓库的分支

![commit-and-push](images/commit-and-push.png)

###  8.3. <a name='commit'></a>回退commit
`git log` 查看日志，复制需要回退的commit号，q退出日志

`git reset commit号` 返回至该commit的本地提交

`git push origin main --force` 用本地仓库覆盖对远程仓库的提交，完成回退 (与本地仓库保持一致)

###  8.4. <a name='-1'></a>同步本地仓库
`git stash` 保存目前更新

`git pull origin/upstream` 本地仓库同步远程仓库/Ocademy仓库

`git stash pop` 恢复目前的更新

###  8.5. <a name='Branch'></a>Branch操作
`git branch` 查看本地仓库的所有分支

`git branch -r` 查看远程仓库的所有分支

`git branch -d branchname` 删除本地仓库的分支

`git branch -d -r branchname(带origin/)` 删除远程仓库的分支 (-d强制删除)

`git checkout branckname` 切换分支

`git checkout -b branchname` 新建本地分支

###  8.6. <a name='vscode'></a>vscode快捷键
`ctrl+shift+p` 输入查找

`ctrl+~` 打开终端

`ctrl+f` 查找文件内容文件 (内容部分)

`ctrl+shift+f` 查找整个项目文件 (目录部分)

##  9. <a name='-1'></a>如何找资料


###  9.1. <a name='Kaggle'></a>Kaggle

Kaggle 有很多不错的

###  9.2. <a name='GitHub'></a>GitHub

License 友好程度：MIT > Apache 2.0 > GNU。其他的遇到了在群里讨论

e.g. 

https://github.com/yandexdataschool/Practical_DL

https://github.com/yandexdataschool/Practical_DL/tree/fall22

https://github.com/rmsouza01/deep-learning/tree/master

https://github.com/aeturrell/coding-for-economists/tree/main

https://github.com/Nyandwi/machine_learning_complete/tree/main

https://github.com/trekhleb/machine-learning-experiments


###  9.3. <a name='Visualization'></a>Visualization



