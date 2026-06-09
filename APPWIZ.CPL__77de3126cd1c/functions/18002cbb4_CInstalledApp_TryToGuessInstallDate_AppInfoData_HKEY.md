# CInstalledApp::_TryToGuessInstallDate(_AppInfoData *,HKEY__ *)

- ea: `0x18002cbb4`
- end: `0x18002ccdf`
- name: `?_TryToGuessInstallDate@CInstalledApp@@AEAAXPEAU_AppInfoData@@PEAUHKEY__@@@Z`
- size: `299`
- prototype: `void(CInstalledApp *__hidden this, struct _AppInfoData *, HKEY)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18002a3e0`

## callees

- `0x180007960`
- `0x18002ca1c`
- `0x18002cbb4`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002cc2f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002cc2f`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18002cc63`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18002cc63`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18002cc75`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18002cc75`

## pseudocode

```c

```
