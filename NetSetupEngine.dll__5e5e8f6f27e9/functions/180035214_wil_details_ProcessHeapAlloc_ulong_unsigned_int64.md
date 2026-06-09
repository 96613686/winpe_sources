# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180035214`
- end: `0x1800352bc`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `168`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003513c`
- `0x18004c0e4`
- `0x180066728`
- `0x180066aac`
- `0x180066be8`
- `0x18006fd5c`

## callees

- `0x180035214`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003527c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003527c`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180035267`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180035267`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180035243`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180035243`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035232`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035232`

## string_xrefs

- `0x180035260`: `ntdll.dll`

## pseudocode

```c

```
