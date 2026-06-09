# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180086728`
- end: `0x1800867be`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800865d8`
- `0x180087360`
- `0x18008749c`

## callees

- `0x180084698`
- `0x180086728`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180086771`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180086771`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008673c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008673c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008674d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008674d`

## string_xrefs

- `0x18008676a`: `ntdll.dll`

## pseudocode

```c

```
