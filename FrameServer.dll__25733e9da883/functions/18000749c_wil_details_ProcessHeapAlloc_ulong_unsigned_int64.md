# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000749c`
- end: `0x180007532`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800068c4`
- `0x180007294`
- `0x1800078d4`
- `0x180007a10`
- `0x18000823c`

## callees

- `0x18000534c`
- `0x18000749c`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800074e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800074e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800074b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800074b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800074c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800074c1`

## string_xrefs

- `0x1800074de`: `ntdll.dll`

## pseudocode

```c

```
