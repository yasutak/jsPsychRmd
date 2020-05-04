
<!-- README.md is generated from README.Rmd. Please edit that file -->

# jsPsychRmd

<!-- badges: start -->

<!-- badges: end -->

jsPsychRmdは，jsPsychをRmarkdownを使って書くための準備をするためのRパッケージです。具体的には，jsPsychで行動課題を作る上で最小構成のスクリプトの入ったRmarkdownテンプレートを準備，jspsych-6.1.0をダウンロードしてフォルダを保存，刺激などをいれるstimuliフォルダを作成します。１行のコードでこれができます。

## インストール

インストールは以下の方法でお願いします（devtoolsが必要です）。

    # install.packages("devtools")
    devtools::install_github("ykunisato/jsPsychRmd")

## 使い方

### RMarkdownとjsPsychで行動課題を作る場合

jsPsychで行動課題を作りたいフォルダに移動して，以下を実行します(folder = TRUE, pavlovia =
FALSEがデフォルトです)。以下の場合だとstroopという名前のフォルダ内に，Rmdファイル(index.Rmdという名前になります)，刺激をいれるstimuliフォルダ（READMEファイルが入っています），jspsych-6.1.0が配置されます。まずは，Rmdファイルを開いて，Knitを押すと，「こんにちは！」が表示されるHTMLファイルが作られます。後は，各種jsPsychのチュートリアルに従ってコードなどを追加していけば，課題が作れます。

    set_jsPsych(file_name = "stroop", folder = TRUE, pavlovia = FALSE)

ちなみに，jsPsychでは日本語表示ができますが，フルスクリーン化のプラグイン（jspsych-fullscreen.js）は英語標記になります。そこで，その日本化版（jspsych-fullscreen\_jp.js）を作成して，上記でダウンロードしたjspsych-6.1.0内に保存しています。jspsych-fullscreen\_jp.jsを使えば，フルスクリーン化の教示も日本語になります。

### RMarkdownとjsPsychで行動課題を作って，pavloviaで実施する場合

RMarkdownとjsPsychで課題を作ってpavloviaで実施する場合，[pavlovia.orgの解説](https://pavlovia.org/docs/experiments/create-jsPsych)を参考に，Pavlovia’s
GitLab repositoryに新しいプロジェクトを作って，ご自身のRStudioで，File→New Project→Version
ControlからGitプロジェクトを作ります（Version Controlでご自身のPavlovia’s GitLab
repositoryの設定情報を入れてください）。その上で，以下を実行してもらうと，そのプロジェクト内に，pavloviaに対応した配置のライブラリとRmdファイルを用意します。あとは課題を作って完成させて，pavloviaにアップしたら実行できます（課題の作成時はコメントアウトしているpavloviaとの連携に関する部分のコメントアウトを外す必要はあります）。

    set_jsPsych(file_name = "stroop", folder = FALSE, pavlovia = TRUE)
