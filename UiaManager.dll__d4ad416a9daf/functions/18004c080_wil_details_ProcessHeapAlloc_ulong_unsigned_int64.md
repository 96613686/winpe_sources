# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18004c080`
- end: `0x18004c11e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010af0`
- `0x180011e10`
- `0x180025618`
- `0x18004bc20`
- `0x18004bd50`
- `0x18004cb20`
- `0x18004cfb0`

## callees

- `0x18004c080`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004c0de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004c0de`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004c0c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004c0c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004c0a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004c0a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c094`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c094`

## string_xrefs

- `0x18004c0c2`: `ntdll.dll`

## pseudocode

```c

```
