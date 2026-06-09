# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000b514`
- end: `0x18000b5b2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009cd8`
- `0x18000a470`
- `0x18000b858`
- `0x180021c08`
- `0x18004b52c`

## callees

- `0x18000b514`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b55d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b55d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b572`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b572`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b528`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b528`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b539`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b539`

## string_xrefs

- `0x18000b556`: `ntdll.dll`

## pseudocode

```c

```
