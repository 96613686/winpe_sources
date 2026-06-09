# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800083bc`
- end: `0x180008465`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006f24`
- `0x180007d2c`
- `0x180007e90`
- `0x1800097a4`
- `0x180009c50`
- `0x18000af94`

## callees

- `0x180004718`
- `0x1800083bc`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008411`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008411`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800083e7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800083e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800083d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800083d0`

## string_xrefs

- `0x18000840a`: `ntdll.dll`

## pseudocode

```c

```
