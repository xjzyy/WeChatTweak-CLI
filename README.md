# WeChatTweak-CLI

A command line utility to work with WeChatTweak-macOS.

## Overview

```bash
OVERVIEW: A command line utility to work with WeChatTweak-macOS.

USAGE: wechattweak-cli <subcommand>

OPTIONS:
  -h, --help              Show help information.

SUBCOMMANDS:
  install                 Install or upgrade tweak.
  uninstall               Uninstall tweak.
  resign                  Force resign WeChat.app
  version                 Get current version of WeChatTweak.

  See 'wechattweak-cli help <subcommand>' for detailed help.
```

## Requirements

- macOS >= 10.12
- Swift 5 Runtime Support

## Install

### Homebrew

You can install [WeChatTweak-CLI](https://github.com/sunnyyoung/WeChatTweak-CLI) via Homebrew.

```bash
$ brew install sunnyyoung/repo/wechattweak-cli
```
```
> brew install sunnyyoung/repo/wechattweak-cli
Running `brew update --auto-update`...

^C
==> Downloading https://github.com/Sunnyyoung/WeChatTweak-CLI/releases/download/1.5/wechattweak-cli
==> Downloading from https://objects.githubusercontent.com/github-production-release-asset-2e65be/40455539
######################################################################## 100.0%
==> Installing Cask wechattweak-cli
==> Linking Binary 'wechattweak-cli' to '/opt/homebrew/bin/wechattweak-cli'
🍺  wechattweak-cli was successfully installed!
```

### 安装/更新/卸载 Tweak:
```
# 安装/更新
sudo wechattweak-cli install
# 卸载
sudo wechattweak-cli uninstall
```
<img width="748" alt="image" src="https://github.com/xjzyy/WeChatTweak-CLI/assets/29560190/63277bb9-db36-4946-aa07-d292ebe63ad9">

```
> sudo wechattweak-cli install
Password:
------ Download ------
------ Unzip ------
Execute command: rm -rf /Applications/WeChat.app/Contents/MacOS/WeChatTweak.framework; unzip /tmp/WeChatTweak.zip -d /Applications/WeChat.app/Contents/MacOS
------ Backup ------
Created WeChat.bak...
------ Remove Codesign ------
Execute command: codesign --remove-sign /Applications/WeChat.app/Contents/MacOS/WeChat
------ Insert Dylib ------
Binary is a fat binary with 2 archs.
Added LC_LOAD_DYLIB to all archs in /Applications/WeChat.app/Contents/MacOS/WeChat
------ Add Codesign ------
Execute command: codesign --force --deep --sign - /Applications/WeChat.app/Contents/MacOS/WeChat
------ Reset ScreenCapture privacy permission ------
Execute command: tccutil reset ScreenCapture com.tencent.xinWeChat
Install success!
```

### Manual (**NOT RECOMMENDED**)

1. Download the [WeChatTweak-CLI](https://github.com/sunnyyoung/WeChatTweak-CLI/releases/latest/download/wechattweak-cli)
2. Remove file attributes: `xattr -d com.apple.quarantine wechattweak-cli`
3. Make sure the binary executable: `chmod +x wechattweak-cli`
4. Run: `sudo ./wechattweak-cli install`

## License

The [Apache License 2.0](LICENSE).
