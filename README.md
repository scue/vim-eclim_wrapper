安装方法
========

主要安装文件是 `plugins/eclim_wrapper/eclim_2.4.1.jar` 文件

    java -jar plugins/eclim_wrapper/eclim_2.4.1.jar

其他文件都是从 `~/.vim` 或 `~/.vim_runtime` 复制过来的，由 `eclim_2.4.1.jar` 自动生成

考虑到`eclim_2.4.1.jar`要在Eclipse上安装插件

所以，更换环境时，还需要执行一次以上的命令行重新安装

现在可以使用 [Vundle](https://github.com/VundleVim/Vundle.vim) 来安装了

一、在你的配置文件上添加:

    if has("gui_running")
        Plugin 'vim-scripts/vim-multiple-cursors'   "  多光标操作
        Plugin 'https://github.com/scue/vim-eclim_wrapper.git' " eclim for ubuntu
    endif

二、然后`cd ~/.vim/bundle/vim-eclim_wrapper`, 执行以下命令，把eclim安装到 Eclipse
    
    java -Dvim.files=$HOME/.vim/bundle/vim-eclim_wrapper \
        -Declipse.home=/path/to/eclipse \
        -jar eclim_2.4.1.jar install 

三、重新打开Eclipse，右击源代码文件，以VIM打开，执行以下命令，就可以完整使用Eclim功能了

    :ProjectCreate <path-to-your-project> -n java
    

由于我只在Ubuntu 14.04 Desktop x64版本上试验这过插件

所以，我不知道其他操作平台能否正常这个插件
