# guidelines

Webサイト制作ガイドライン（テスト）

https://test.com/docs/guidelines/

使用しているフォントファイルは含んでいません。

- Font Awesome 4.3.0 by @davegandy http://fontawesome.io
- Google Not Fonts https://www.google.com/get/noto/

使い方
```
git config --global user.name "ユーザ名"
git config --global user.email メールアドレス
cd '/Users/Atsushi/Library/Mobile Documents/com~apple~CloudDocs/Documents/github/guidelines/'
echo "# guidelines" >> README.md
git init
git add README.md
git commit -m "first commit"

// GitHubへプッシュ
git remote add origin https://github.com/rtyrt519/guidelines.git
git push -u origin master
```
http://www.atmarkit.co.jp/ait/articles/1604/26/news019.html

## gitの基本的な作業フロー(http://www.atmarkit.co.jp/ait/series/3190/)


### 3つの場所
1. Gitリポジトリ（Git Repository）
 - ファイルのスナップショットなどを保存する領域
実態は「作業ディレクトリ」の中の「.gitディレクトリ」
- 作業ディレクトリ（Working Directory）
 - ファイルの編集作業を行うディレクトリ
Gitを使ったバージョン管理では、作業ディレクトリ内のファイルの変更履歴を保存していく
- ステージングエリア（Staging Area）
 - 「作業ディレクトリ」と「Gitリポジトリ」の中間に存在する領域。「インデックス」と呼ばれることもある
コミットする準備ができたファイルはここに追加する



### 作業フロー
1. 「作業ディレクトリ」上のファイルを変更する （作業ディレクトリ）
 - あるいはファイルを新たに追加する
+ 変更済みのファイルを``ステージする``(作業ディレクトリ→ステージングエリア)
 - 「git add」コマンドを使用して「変更済みのファイル」を「ステージングエリア」に追加する
+ ステージ済みのファイルを``コミットする``（ステージングエリア→Gitリポジトリ）
 - 「git commit」コマンドを使用して、手順2でステージしたファイルの「スナップショット」を「Gitリポジトリ」に保存する)

## 3つの状態
1. 追跡済み（tracked）：Gitが変更を追跡しているファイル
 - 未変更（unmodified）
スナップショットがリポジトリに保存されているファイル
 - 変更済み（modified）
Gitが変更を追跡しているが、変更がリポジトリに保存されていないファイル
 - ステージ済み（staged）
ステージングエリアに追加され、次回コミットの対象となっているファイル
- 未追跡（untracked）：Gitが変更を追跡していないファイル

```
// ディレクトリをつくる
mkdir hello-git
cd hello-git

// Gitリポジトリを準備
git init
git status

On branch master
Initial commit
nothing to commit

// ファイルを作成
echo Hello > hello.txt
git status

On branch master
Initial commit
Untracked files:
	hello.txt

// ステージする
git add hello.txt
git status

On branch master
Initial commit
Changes to be committed:
	new file:   hello.txt

// コミットする
git commit -m "first commit"
git status

On branch master
nothing to commit, working directory clean
```

```
// ファイルを変更する
echo goodbye >> hello.txt
git status

On branch master
Changes not staged for commit:
	modified:   hello.txt

// ステージする
git add hello.txt
git status

On branch master
Changes to be committed:
    modified:   hello.txt

// コミットする
git commit -m "edit hello.txt"
git status

On branch master
nothing to commit, working directory clean
```
