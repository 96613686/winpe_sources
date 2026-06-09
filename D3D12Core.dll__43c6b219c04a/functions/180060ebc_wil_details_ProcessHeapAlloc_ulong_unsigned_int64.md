# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180060ebc`
- end: `0x180060f5a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800a8a6c`
- `0x1800c4d64`
- `0x1800c4e88`
- `0x1800c5c90`
- `0x1800c6028`

## callees

- `0x180060ebc`
- `0x180262020`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060f1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060f1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180060f05`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180060f05`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060ee1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060ee1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060ed0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060ed0`

## string_xrefs

- `0x180060efe`: `ntdll.dll`

## pseudocode

```c

```
