# ACUtil::GetFullAppContainerNamedObjectPath(void *,ushort const *,ulong,ushort *)

- ea: `0x180066f20`
- end: `0x18006703f`
- name: `?GetFullAppContainerNamedObjectPath@ACUtil@@SAJPEAXPEBGKPEAG@Z`
- size: `287`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180066418`
- `0x1800666a4`
- `0x180067048`

## callees

- `0x180035dd8`
- `0x180061320`
- `0x180066f20`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180066f5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180066f5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066f94`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180066f94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066f6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066fdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066f6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066fdf`

## string_xrefs

- `0x180066f50`: `kernel32.dll`
- `0x180066f8a`: `GetAppContainerNamedObjectPath`

## pseudocode

```c

```
