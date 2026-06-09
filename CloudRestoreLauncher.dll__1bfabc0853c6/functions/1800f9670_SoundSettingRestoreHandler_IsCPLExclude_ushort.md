# SoundSettingRestoreHandler::IsCPLExclude(ushort *)

- ea: `0x1800f9670`
- end: `0x1800f9859`
- name: `?IsCPLExclude@SoundSettingRestoreHandler@@AEAA_NPEAG@Z`
- size: `489`
- prototype: `bool __fastcall(SoundSettingRestoreHandler *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800f9a68`

## callees

- `0x18000c6e0`
- `0x1800124b4`
- `0x1800284d0`
- `0x1800977e8`
- `0x1800f8f68`
- `0x1800f91d8`
- `0x1800f9670`
- `0x1800fa8b4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800f96f8`
- `ADVAPI32!RegOpenKeyExW` at `0x1800f96f8`
- `ADVAPI32!RegCloseKey` at `0x1800f9835`
- `ADVAPI32!RegCloseKey` at `0x1800f9835`
- `ADVAPI32!RegQueryValueExW` at `0x1800f9769`
- `ADVAPI32!RegQueryValueExW` at `0x1800f9769`

## pseudocode

```c

```
