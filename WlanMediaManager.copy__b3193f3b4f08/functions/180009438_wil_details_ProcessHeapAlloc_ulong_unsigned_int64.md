# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180009438`
- end: `0x1800094ce`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000879c`
- `0x1800091b0`
- `0x180009860`
- `0x180009bf8`
- `0x18002cbe0`
- `0x18002e520`

## callees

- `0x18000707c`
- `0x180009438`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009481`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009481`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000944c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000944c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000945d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000945d`

## string_xrefs

- `0x18000947a`: `ntdll.dll`

## pseudocode

```c

```
