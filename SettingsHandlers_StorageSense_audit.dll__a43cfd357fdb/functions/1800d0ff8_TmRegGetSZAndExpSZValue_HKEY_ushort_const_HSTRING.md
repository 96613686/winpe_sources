# TmRegGetSZAndExpSZValue(HKEY__ *,ushort const *,HSTRING__ * *)

- ea: `0x1800d0ff8`
- end: `0x1800d10f4`
- name: `?TmRegGetSZAndExpSZValue@@YAJPEAUHKEY__@@PEBGPEAPEAUHSTRING__@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, HSTRING *string)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800d5540`

## callees

- `0x1800d0ff8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d1069`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d10d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d1069`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d10d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d10df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d10df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d107a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d107a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d10c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d10c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d102e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d10af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d102e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d10af`

## pseudocode

```c

```
