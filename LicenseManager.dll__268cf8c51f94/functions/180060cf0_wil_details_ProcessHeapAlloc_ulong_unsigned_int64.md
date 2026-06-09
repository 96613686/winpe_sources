# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180060cf0`
- end: `0x180060d8e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180060aa0`
- `0x180060bd8`
- `0x180062768`
- `0x180083490`
- `0x1800835cc`

## callees

- `0x180060cf0`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060d4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180060d4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180060d39`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180060d39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060d04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060d04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060d15`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060d15`

## string_xrefs

- `0x180060d32`: `ntdll.dll`

## pseudocode

```c

```
