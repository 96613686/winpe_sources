# SystemSettings::Personalization::BackgroundChooseBackground::RestoreCurrentWallpaperFromRegistry(void)

- ea: `0x180121c00`
- end: `0x180121dfd`
- name: `?RestoreCurrentWallpaperFromRegistry@BackgroundChooseBackground@Personalization@SystemSettings@@AEAAJXZ`
- size: `509`
- prototype: `__int64 __fastcall(SystemSettings::Personalization::BackgroundChooseBackground *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180126da4`

## callees

- `0x18000c840`
- `0x180011bb0`
- `0x180019a20`
- `0x18001a64c`
- `0x180121c00`
- `0x180197d50`
- `0x180198a88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180121c86`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180121d2a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180121c86`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180121d2a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180121da8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180121da8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180121cba`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180121d85`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180121cba`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180121d85`

## string_xrefs

- `0x180121ccf`: `BackgroundHistoryPath`
- `0x180121c71`: `CurrentWallpaperPath`

## pseudocode

```c

```
