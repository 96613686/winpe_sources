# SetProxyInfoManualBypassList(ushort *)

- ea: `0x140030bb4`
- end: `0x140030cd2`
- name: `?SetProxyInfoManualBypassList@@YAJPEAG@Z`
- size: `286`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400309e0`

## callees

- `0x140005f54`
- `0x140005f84`
- `0x14001f3d4`
- `0x140030bb4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140030ca3`
- `KERNEL32!GetLastError` at `0x140030ca3`
- `WININET!InternetQueryOptionW` at `0x140030c52`
- `WININET!InternetQueryOptionW` at `0x140030c52`
- `WININET!InternetSetOptionW` at `0x140030c84`
- `WININET!InternetSetOptionW` at `0x140030c9b`
- `WININET!InternetSetOptionW` at `0x140030c84`
- `WININET!InternetSetOptionW` at `0x140030c9b`

## string_xrefs

- `0x140030c16`: `pcshell\shell\systemsettings\adminflows\common\proxyconfighandler.cpp`

## pseudocode

```c

```
