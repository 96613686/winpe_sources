# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000f010`
- end: `0x18000f0a6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000d18c`
- `0x18000e754`
- `0x18000e8b8`
- `0x180010ccc`
- `0x18001118c`
- `0x180013ddc`

## callees

- `0x180005fe0`
- `0x18000f010`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f059`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f059`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f035`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f035`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f024`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f024`

## string_xrefs

- `0x18000f052`: `ntdll.dll`

## pseudocode

```c

```
