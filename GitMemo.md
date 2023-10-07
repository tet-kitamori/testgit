# Gitに関するメモ
## 0. Gitのバージョン
Gitのバージョン確認は、$git --version または git -v
## 1. Gitの設定
### 1.1 Gitの設定確認

`$ git config [--system|--global|--local|-f <config_file> ] [--show-origin] -l`

  例えば、

### ユーザ範囲の設定

C:/Users/**username**/.gitconfig

`$ git config --global -l`　　(-lは--listの省略形)

- core.editor="C:\Users\tetki\AppData\Local\Programs\Microsoft VS Code\bin\code" --wait
- gui.recentrepo=C:/myWork/JavaScP/hellogit
- filter.lfs.smudge=git-lfs smudge -- %f
- filter.lfs.process=git-lfs filter-process
- filter.lfs.required=true
- filter.lfs.clean=git-lfs clean -- %f
- user.name=tet-kitamori
- user.email=tetkita2021@outlook.jp



### システム設定(すべてのユーザに共通)

C:/Program Files/Git/etc/gitconfigに格納

`$git config --system -l`

- diff.astextplain.textconv=astextplain
- filter.lfs.clean=git-lfs clean -- %f
- filter.lfs.smudge=git-lfs smudge -- %f
- filter.lfs.process=git-lfs filter-process
- filter.lfs.required=true
- http.sslbackend=openssl
- http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
- core.autocrlf=true
- core.fscache=true
- core.symlinks=false
- pull.rebase=false
- credential.helper=manager-core
- credential.https://dev.azure.com.usehttppath=true
- init.defaultbranch=master

### リポジトリ固有設定

.git/configに格納 ※リポジトリのフォルダ直下に隠しフォルダ.gitが存在している

`$git config --local -l`

### すべての設定の設定範囲を表示

`$ git config --show-origin -l`

### 1.2 設定の変更、追加

`$ git config [--system|--global|--local|-f <config_file>] <name> <value>`

例

`$ git config --global user.email mailuser@xxxx.com`

### 1.3 設定の削除

`$ git config [--system|--global|--local|-f <config_file>] [--unset|--unset-all|--remove-section] <name>[<value>]`

設定を削除する例

カレントユーザの設定にユーザのemailを削除する。

`$ git config --global --unset user.email`

カレントユーザの設定にuserセクションを削除する。

`$ git config --global --remove-section user`

