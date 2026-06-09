# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800030ec`
- end: `0x180003182`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(unsigned int flags, unsigned __int64 size)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001a7c`
- `0x180001ae4`
- `0x180028e7c`
- `0x18003187c`
- `0x180033d28`

## callees

- `0x1800030ec`
- `0x18002898c`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003135`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003135`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003111`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003111`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003100`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003100`

## string_xrefs

- `0x18000312e`: `ntdll.dll`

## pseudocode

```c

```
