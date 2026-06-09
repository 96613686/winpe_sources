# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180138cd4`
- end: `0x180138d72`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800f9dd4`
- `0x180138798`
- `0x1801388bc`
- `0x1801398f0`
- `0x180139d74`

## callees

- `0x180138cd4`
- `0x1801c7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180138d32`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180138d32`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180138d1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180138d1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180138ce8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180138ce8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180138cf9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180138cf9`

## string_xrefs

- `0x180138d16`: `ntdll.dll`

## pseudocode

```c

```
