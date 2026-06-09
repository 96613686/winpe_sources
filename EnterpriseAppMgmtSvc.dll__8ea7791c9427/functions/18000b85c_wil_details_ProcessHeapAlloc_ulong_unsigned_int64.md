# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000b85c`
- end: `0x18000b8fa`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a3b8`
- `0x18000e2cc`
- `0x1800298b4`
- `0x18002e170`

## callees

- `0x18000b85c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b8ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b8ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b8a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b8a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b881`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b881`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b870`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b870`

## string_xrefs

- `0x18000b89e`: `ntdll.dll`

## pseudocode

```c

```
