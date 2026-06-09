# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000bdf0`
- end: `0x18000be86`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000aa7c`
- `0x18000b804`
- `0x18000b968`
- `0x18000cd30`
- `0x18000d1c0`
- `0x18000e42c`

## callees

- `0x1800088c4`
- `0x18000bdf0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000be39`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000be39`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000be15`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000be15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be04`

## string_xrefs

- `0x18000be32`: `ntdll.dll`

## pseudocode

```c

```
