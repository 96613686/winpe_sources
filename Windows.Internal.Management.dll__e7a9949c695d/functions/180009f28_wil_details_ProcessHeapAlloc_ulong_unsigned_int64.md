# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180009f28`
- end: `0x180009fbe`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800092dc`
- `0x180009ca8`
- `0x18000a350`
- `0x18000a6e8`
- `0x18000fe5c`
- `0x180012c90`

## callees

- `0x180007c80`
- `0x180009f28`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009f71`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009f71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009f4d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009f4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f3c`

## string_xrefs

- `0x180009f6a`: `ntdll.dll`

## pseudocode

```c

```
