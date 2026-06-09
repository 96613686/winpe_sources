# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000698c`
- end: `0x180006a22`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005c4c`
- `0x1800066f8`
- `0x180006f54`
- `0x180007090`
- `0x180012518`
- `0x180019cb8`

## callees

- `0x180004490`
- `0x18000698c`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800069d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800069d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800069b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800069b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800069a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800069a0`

## string_xrefs

- `0x1800069ce`: `ntdll.dll`

## pseudocode

```c

```
