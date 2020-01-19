# electron-virustotal

#### PoC for false positives in an Electron app

This is a minimal Electron app based on the official guide: https://github.com/electron/electron-quick-start.

[Modifications](https://github.com/thisismydesign/electron-virustotal/compare/314187368b5d789fb4e6fba876be578c7b770396..master):
- added `electron-builder` as dev-dependency

## Usage

On windows

```
npm install
npm audit
npm run build
```

Check `dist/electron-quick-start Setup 1.0.0.exe` against virustotal.com: https://www.virustotal.com/gui/file/d4a7f2f6483ca41621230294640bf7f09d2160ae0c99c06fc3d02bb48381862d/detection

```
2020-01-19 17:29:37 UTC
Bkav HW32.Packed.
```

Workarounds tested:
- [`useZip` option](https://github.com/electron-userland/electron-builder/issues/550#issuecomment-292955681) - same result

Clean runs with other Electron products:
- [Discord](https://www.virustotal.com/gui/file/574911f80b7919426ad62a8188b78a6e1028cae534dbd1edde1f540a9b2bb665/detection)
- [Slack](https://www.virustotal.com/gui/file/d8424e45a0a5dccde8c83fed408ffc674fd40b9f1643d6b875bd7f3f1473cc54/detection)

Similar issues:
- https://github.com/electron-react-boilerplate/electron-react-boilerplate/issues/1597
- https://github.com/chrisknepper/android-messages-desktop/issues/47
- https://github.com/chainmakers/chainmakers-ui-mono-repository/issues/18
