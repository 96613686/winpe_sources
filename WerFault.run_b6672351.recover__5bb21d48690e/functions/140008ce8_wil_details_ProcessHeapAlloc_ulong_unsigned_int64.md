# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140008ce8`
- end: `0x140008d9f`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400062cc`
- `0x1400066a8`
- `0x14000b100`
- `0x14000cc9c`

## callees

- `0x140008ce8`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008d3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008d3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008d58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008d58`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008d13`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008d13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008cfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008cfc`

## string_xrefs

- `0x140008d36`: `ntdll.dll`

## pseudocode

```c

```
