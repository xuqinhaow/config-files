# config-files

Contains config files below.

1. vim config for Mac OS X/Win7/Ubuntu via Vundle.

2. stl views support for gdb.

3. stl tags file generate from <http://www.vim.org/scripts/script.php?script_id=2358>.

4. emacs config for Win7.

The Quick Start below is just for self use, I don't promise it will work well in your environment.

## Table of Contents

* [Quick Start](#quick-start)
	* [Mac OS X](#mac-os-x)
		* [Vim](#vim)
		* [Emacs](#emacs)
	* [Windows](#windows)
		* [Vim](#vim-1)
		* [Emacs](#emacs-1)
	* [Ubuntu](#ubuntu)

## Quick Start

### Mac OS X

#### Vim

* Set up Vundle:

    ```
    git clone https://github.com/gmarik/Vundle.vim.git ~/vimfiles/bundle/Vundle.vim
    ```

* install cscope

	If you want to view code, you may need cscope support, so install it.

    ```
    brew install cscope
    ```

* generate tags files (*optional*)

	For better c++ coding experience, generate your crttags and win32tags into ~/tags-files dir.

* pull config files:

    ```
    cd ~
    git init
    git remote add origin https://github.com/mzlogin/config-files.git
    git pull origin master
    ```

* Install plugins

	Start vim, and exec `:PluginInstall`

* Build YouCompleteMe plugin

    Confirm you have `libclang.dylib`, and then

    ```
    brew install cmake
    cd ~/vimfiles/bundle/YouComplete
    git submodule update --init --recursive
    ./install.sh --clang-completer --system-libclang
    ```

* Done!

#### Emacs

* install the newest version of GNU Emacs, global and sbcl

    ```
    brew install emacs
    brew install global
    brew install sbcl
    ```
* create file /usr/bin/sbcl and change its content to

    ```
    #!/bin/sh
    exec /usr/local/bin/sbcl "$@"
    ```

* copy c++ headers into ~/.emacs.d/cpp-headers

* use elpa in Emacs to install plugins below:

    * company

    * ggtags

	* helm-gtags

    * markdown-mode

	* projectile

	* sr-speedbar

	* smex

	* evil

	* jedi
		* pip install virtualenv
	    * M-x package-install <RETURN> jedi <RETURN>
		* M-x package-install <RETURN> exec-path-from-shell <RETURN>
		* restart emacs
		* M-x exec-path-from-shell-initialize
		* M-x jedi:install-server

	* evil-nerd-commenter

	* function-args

	* slime

	* slime-company

	* smooth-scrolling

    For example to install ggtags:

    ```
    M-x package-install <RETURN>
    ggtags <RETURN>
    ```

### Windows

#### Vim

* Set up Vundle:

    ```
    git clone https://github.com/gmarik/Vundle.vim.git %userprofile%/vimfiles/bundle/Vundle.vim
    ```

* place ctags.exe

	The plugin taglist required **Exuberant Ctags**, so download it, and put it into YourVimInstallPath/vim74/ directory.

    (You can download ctags and cscope I am used [here](http://pan.baidu.com/s/1c06ucTi).)

* place cscope.exe (*optional*)

	If you want to view code, you may need cscope support, put it into YourVimInstallPath/vim74/ directory.(It may depend on regex2.dll and curses2.dll)

* generate tags files (*optional*)

	For better c++ coding experience, generate your crttags and win32tags into ~/tags-files dir.

* pull config files:

    ```
    cd %userprofile%
    git init
    git remote add origin https://github.com/mzlogin/config-files.git
    git pull origin master
    ```

* Install plugins

	Start vim, and exec `:PluginInstall`

* place iconv.dll

    The plugin fencview, for file encoding detect and switch, required this dll, so download one and add its path to PATH environment variable.

    (You can download iconv.dll I am used [here](http://pan.baidu.com/s/1pJGOpCJ).)

* Config YouCompleteMe (*optional*)
    * Install LLVM/Clang for windows and add libclang.dll path to PATH environment variable.
    * Download [Vim YouCompleteMe for Windows](https://bitbucket.org/Alexander-Shukaev/vim-youcompleteme-for-windows), and then unzip it to %userprofile%/vimfiles/bundle/YouCompleteMe.

    **Notice:** Your Vim/Clang/YCM should be all x86 or all x64, keep them consistent.

    **You may meet some pitfalls in this step, keep easy and see Overview and Issues in the above link.**

* Done!

#### Emacs

* get GNU Emacs in <http://www.gnu.org/software/emacs/>.

* add "Edit with Emacs" to context menu with .reg file (replace exe file path to yours first):

	```
	Windows Registry Editor Version 5.00

	[HKEY_CLASSES_ROOT\*\shell\Edit with Emacs]

	[HKEY_CLASSES_ROOT\*\shell\Edit with Emacs\command]
	@="\"D:\\emacs\\bin\\emacsclientw.exe\" -a \"D:\\emacs\\bin\\runemacs.exe\" \"%1\""
	```

* download GNU Global from <http://www.gnu.org/software/global/>, and copy files to Emacs directory.

* download sbcl from <http://www.sbcl.org/> and install it to default path.

* copy c++ headers into ~/.emacs.d/cpp-headers

* use elpa in Emacs to install plugins below:
    
    * company

    * ggtags

	* helm-gtags

    * markdown-mode

	* projectile

	* sr-speedbar

	* smex

	* evil

	* jedi
		* pip install virtualenv
	    * M-x package-install <RETURN> jedi <RETURN>
		* M-x package-install <RETURN> exec-path-from-shell <RETURN>
		* restart emacs
		* M-x exec-path-from-shell-initialize
		* M-x jedi:install-server

	* evil-nerd-commenter

	* function-args

	* slime

	* slime-company

	* smooth-scrolling

    For example to install ggtags:

    ```
    M-x package-install <RETURN>
    ggtags <RETURN>
    ```

### Ubuntu

* Set up Vundle:

    ```
    git clone https://github.com/gmarik/Vundle.vim.git ~/vimfiles/bundle/Vundle.vim
    ```

* install ctags

	The plugin taglist required ctags, so install it.

    ```
    sudo apt-get install exuberant-ctags
    ```

* install cscope

	If you want to view code, you may need cscope support, so install it.

    ```
    sudo apt-get install cscope
    ```

* generate tags files (*optional*)

	For better c++ coding experience, generate your crttags and win32tags into ~/tags-files dir.

* pull config files:

    ```
    cd ~
    git init
    git remote add origin https://github.com/mzlogin/config-files.git
    git pull origin master
    ```

* Install plugins

	Start vim, and exec `:PluginInstall`

* Done!
