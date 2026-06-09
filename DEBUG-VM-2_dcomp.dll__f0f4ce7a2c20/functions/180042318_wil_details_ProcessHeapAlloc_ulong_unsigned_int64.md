# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180042318`
- end: `0x1800423b9`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `161`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180042258`
- `0x1800ecd44`
- `0x1800f92cc`
- `0x1800f93fc`
- `0x1800f9834`

## callees

- `0x180042318`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800423aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800423aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180042380`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180042380`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004233d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004233d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004232c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004232c`

## string_xrefs

- `0x180042379`: `ntdll.dll`

## pseudocode

```c

```
