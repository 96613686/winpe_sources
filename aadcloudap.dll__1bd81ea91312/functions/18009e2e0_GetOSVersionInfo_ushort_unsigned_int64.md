# GetOSVersionInfo(ushort *,unsigned __int64)

- ea: `0x18009e2e0`
- end: `0x18009e4a6`
- name: `?GetOSVersionInfo@@YAJPEAG_K@Z`
- size: `454`
- prototype: `__int64 __fastcall(wchar_t *Buffer, size_t BufferCount)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800973f8`
- `0x18009da38`

## callees

- `0x180003c20`
- `0x180004a24`
- `0x1800061d4`
- `0x180086a54`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aecc`
- `0x18009e2e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e41e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e41e`
- `ntdll!RtlGetVersion` at `0x18009e378`
- `ntdll!RtlGetVersion` at `0x18009e378`

## string_xrefs

- `0x18009e3db`: `RegReadDwordValue`

## pseudocode

```c

```
