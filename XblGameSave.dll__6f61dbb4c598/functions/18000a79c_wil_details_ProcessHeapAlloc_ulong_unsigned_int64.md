# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000a79c`
- end: `0x18000a83a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a4b0`
- `0x18000b08c`
- `0x18000b424`
- `0x1800234e0`
- `0x180026548`

## callees

- `0x18000a79c`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a7c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a7c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a7b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a7b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a7fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a7fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a7e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a7e5`

## string_xrefs

- `0x18000a7de`: `ntdll.dll`

## pseudocode

```c

```
