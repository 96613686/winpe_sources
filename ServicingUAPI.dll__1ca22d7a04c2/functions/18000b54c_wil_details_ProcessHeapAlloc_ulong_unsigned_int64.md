# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000b54c`
- end: `0x18000b60d`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `193`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009b4c`
- `0x18000a7dc`
- `0x18000bf78`
- `0x180039c94`
- `0x18003c854`

## callees

- `0x18000b54c`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000b5c6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000b5c6`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000b5ab`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000b5ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b581`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b581`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b56a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b56a`

## string_xrefs

- `0x18000b5a4`: `ntdll.dll`

## pseudocode

```c

```
