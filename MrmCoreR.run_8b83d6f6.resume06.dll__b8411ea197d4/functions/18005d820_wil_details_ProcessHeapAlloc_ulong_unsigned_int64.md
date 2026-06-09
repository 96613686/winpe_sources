# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18005d820`
- end: `0x18005d8be`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18005ba04`
- `0x18005d778`
- `0x1800727a4`
- `0x180089c2c`
- `0x180089fb0`

## callees

- `0x18005d820`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005d87e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005d87e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005d869`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005d869`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005d845`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005d845`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005d834`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005d834`

## string_xrefs

- `0x18005d862`: `ntdll.dll`

## pseudocode

```c

```
