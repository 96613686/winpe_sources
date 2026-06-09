# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180062008`
- end: `0x18006209e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002df60`
- `0x18009bfdc`
- `0x18009c174`
- `0x1800bc8bc`
- `0x1800bcc54`

## callees

- `0x180062008`
- `0x1800aca40`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180062051`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180062051`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006201c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006201c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006202d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006202d`

## string_xrefs

- `0x18006204a`: `ntdll.dll`

## pseudocode

```c

```
