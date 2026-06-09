# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000e88c`
- end: `0x18000e922`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000e7e8`
- `0x18001af10`
- `0x18001d978`
- `0x180030cb0`
- `0x1800311b8`
- `0x18003a2cc`
- `0x18003a3fc`

## callees

- `0x18000e88c`
- `0x180039470`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e8d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e8d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e8b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e8b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e8a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e8a0`

## string_xrefs

- `0x18000e8ce`: `ntdll.dll`

## pseudocode

```c

```
