# Microsoft.VisualStudio.Setup.LatestInstallerFeedManager::.cctor

- ea: `0x14a90`
- end: `0x14abe`
- name: `Microsoft.VisualStudio.Setup.LatestInstallerFeedManager::.cctor`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0x14a90`: `.json`
- `0x14a9a`: `https://aka.ms/vs/installer/latest/feed`
- `0x14aa9`: `latestInstaller.json`
- `0x14ab3`: `_LatestInstaller`

## pseudocode

```c

```

## disassembly

```asm
0x14a90  ldstr    aJson// ".json"
0x14a95  stsfld   string Microsoft.VisualStudio.Setup.LatestInstallerFeedManager::LatestInstallerFeedFileExtension
0x14a9a  ldstr    aHttpsAkaMsVsIn// "https://aka.ms/vs/installer/latest/feed"
0x14a9f  newobj   instance void [System]System.Uri::.ctor(string)
0x14aa4  stsfld   class [System]System.Uri Microsoft.VisualStudio.Setup.LatestInstallerFeedManager::LatestInstallerFeedUri
0x14aa9  ldstr    aLatestinstalle// "latestInstaller.json"
0x14aae  stsfld   string Microsoft.VisualStudio.Setup.LatestInstallerFeedManager::LatestInstallerFeedFileName
0x14ab3  ldstr    aLatestinstalle_0// "_LatestInstaller"
0x14ab8  stsfld   string Microsoft.VisualStudio.Setup.LatestInstallerFeedManager::SubdirectoryName
0x14abd  ret
```
