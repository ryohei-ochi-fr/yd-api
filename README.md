# 環境構築

以下のコマンドをインストールする

- scoop
- hub
- gibo

参考サイト
[GitHub のコマンドラインツール「hub」の基本と便利な使い方のまとめ | DevelopersIO](https://dev.classmethod.jp/articles/hub/)  
[github/hub: A command-line tool that makes git easier to use with GitHub.](https://github.com/github/hub)  
[ScoopInstaller/Scoop: A command-line installer for Windows.](https://github.com/ScoopInstaller/Scoop)  

```powershell
Invoke-Expression (New-Object System.Net.WebClient).DownloadString('https://get.scoop.sh')
scoop --version
scoop update
scoop install hub
hub --version
scoop install gibo
gibo version
```

PowerShellでhubをgitのエイリアスに設定するのが公式だけど、明確にhubコマンドを利用する方針とするー

```powershell
Set-Alias git hub
```

## リポジトリ作成

作業フォルダを用意する(フォルダ名は任意、リポジトリ名になる)

```powershell
mkdir project-name
cd project-name
git init
git config user.name ryohei-ochi-f
git config user.name
git config user.email ryohei.ochi@futurerays.biz
git config user.email
gibo update
gibo dump Node VisualStudioCode > .gitignore
code .
```

github に、リポジトリ(remote)を作成する

```powershell
git create
```

認証エラーとなる場合はhubの設定ファイルを確認する

```powershell
type ~/.config/hub
```

```shell
PS > git remote -v
origin  git@github.com:ryohei-ochi-fr/project-name.git (fetch)
origin  git@github.com:ryohei-ochi-fr/project-name.git (push)
```

ブラウザでリモートリポジトリを確認する

```powershell
hub browse
```

## first commit

```powershell
git add .
git commit -m "first commit"
git status

git branch

git branch -m master
git push -u origin master
```
