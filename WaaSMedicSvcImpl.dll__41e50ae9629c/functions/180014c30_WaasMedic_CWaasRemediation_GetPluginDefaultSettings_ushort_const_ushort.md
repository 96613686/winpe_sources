# WaasMedic::CWaasRemediation::GetPluginDefaultSettings(ushort const *,ushort * *)

- ea: `0x180014c30`
- end: `0x180014da5`
- name: `?GetPluginDefaultSettings@CWaasRemediation@WaasMedic@@AEAAJPEBGPEAPEAG@Z`
- size: `373`
- prototype: `__int64 __fastcall(WaasMedic::CWaasRemediation *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800128ac`

## callees

- `0x1800050a0`
- `0x18000bbd4`
- `0x18001039c`
- `0x180014c30`
- `0x18002e56c`
- `0x18002e81c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014cbb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014d32`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014cbb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014d32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d59`

## string_xrefs

- `0x180014ce6`: `Attempting to fallback from %s to %s`
- `0x180014d4a`: `GetPluginDefaultSettings not found`

## pseudocode

```c

```
