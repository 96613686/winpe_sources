# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800085f8`
- end: `0x180008696`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006df8`
- `0x1800075a0`
- `0x180008ad4`
- `0x180039194`
- `0x18003c264`

## callees

- `0x1800085f8`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008641`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008641`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008656`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008656`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000860c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000860c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000861d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000861d`

## string_xrefs

- `0x18000863a`: `ntdll.dll`

## pseudocode

```c

```
