# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800676a8`
- end: `0x18006773e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18006694c`
- `0x18006741c`
- `0x180067b00`
- `0x180067e98`
- `0x1800731b0`
- `0x180077dcc`

## callees

- `0x180064d24`
- `0x1800676a8`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800676f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800676f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800676cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800676cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800676bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800676bc`

## string_xrefs

- `0x1800676ea`: `ntdll.dll`

## pseudocode

```c

```
