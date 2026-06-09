# CreateACLedUserTileFolderandRegKey(ushort const *)

- ea: `0x18004c994`
- end: `0x18004cae8`
- name: `?CreateACLedUserTileFolderandRegKey@@YAJPEBG@Z`
- size: `340`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800c9638`

## callees

- `0x18002be34`
- `0x18003aa84`
- `0x18004c994`
- `0x180050ba0`
- `0x1800c2fa0`
- `0x1800d3d80`
- `0x1800d40fc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004caa4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004caa4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x18004ca70`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x18004ca70`
- `SHCORE!__imp_SHCreateDirectoryExW` at `0x18004ca36`
- `SHCORE!__imp_SHCreateDirectoryExW` at `0x18004ca36`
- `SHELL32!SHSetLocalizedName` at `0x18004ca52`
- `SHELL32!SHSetLocalizedName` at `0x18004ca97`
- `SHELL32!SHSetLocalizedName` at `0x18004ca52`
- `SHELL32!SHSetLocalizedName` at `0x18004ca97`

## string_xrefs

- `0x18004ca69`: `%ProgramData%\Microsoft\User Account Pictures`
- `0x18004ca46`: `Windows.UI.Immersive.dll`
- `0x18004ca8b`: `Windows.UI.Immersive.dll`

## pseudocode

```c

```
