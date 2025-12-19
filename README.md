# git-graph-tui

CLIでGitグラフを表示するTUIツール。VSCode Git Graph拡張機能のようなブランチツリー表示をターミナルで実現します。

## 機能

- **グラフ表示**: Unicode Box Drawing文字によるリッチなブランチグラフ
- **ブランチ操作**: checkout、ブランチ作成・削除、merge、rebase
- **インタラクティブ**: vi風キーバインドでのナビゲーション
- **カラー表示**: ブランチごとに異なる色で識別

## スクリーンショット

```
┌───────────────┬─────────────────────────────────────────────────────┐
│ Branches      │  Commits                                            │
│               │                                                     │
│  ● main      │  ●   d2f1ac7 trasta     12-20 Add develop file      │
│  ○ develop   │  │ ● 3f1824e trasta     12-20 Add test file         │
│  ○ feature/x │  ├─╯                                                 │
│               │  ●   2600310 trasta     12-20 Add .gitignore        │
│               │  ●   f0b7da0 trasta     12-20 Initial commit        │
└───────────────┴─────────────────────────────────────────────────────┘
```

## インストール

```bash
cargo install --path .
```

または

```bash
cargo build --release
./target/release/git-graph-tui
```

## 使い方

Gitリポジトリ内で実行:

```bash
git-graph-tui
```

## キーバインド

### ナビゲーション

| キー | 説明 |
|------|------|
| `j` / `↓` | 下へ移動 |
| `k` / `↑` | 上へ移動 |
| `h` / `←` | ブランチリストへフォーカス |
| `l` / `→` | グラフへフォーカス |
| `Ctrl+d` | 半ページ下スクロール |
| `Ctrl+u` | 半ページ上スクロール |
| `g` / `Home` | 先頭へ移動 |
| `G` / `End` | 末尾へ移動 |
| `Tab` | フォーカス切替 |

### Git操作

| キー | 説明 |
|------|------|
| `Enter` | 選択中のブランチ/コミットをcheckout |
| `b` | 新規ブランチ作成 |
| `d` | ブランチ削除 |
| `m` | 選択ブランチをマージ |
| `r` | 選択ブランチにリベース |

### その他

| キー | 説明 |
|------|------|
| `R` | リポジトリ情報を更新 |
| `?` | ヘルプ表示 |
| `q` / `Esc` | 終了 |

## 依存クレート

- [ratatui](https://github.com/ratatui/ratatui) - TUIフレームワーク
- [crossterm](https://github.com/crossterm-rs/crossterm) - クロスプラットフォームターミナル
- [git2](https://github.com/rust-lang/git2-rs) - libgit2バインディング
- [clap](https://github.com/clap-rs/clap) - CLI引数パーサー
- [chrono](https://github.com/chronotope/chrono) - 日時処理

## ライセンス

MIT
