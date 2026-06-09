# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180041100`
- end: `0x180041196`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180008e70`
- `0x180031814`
- `0x18003fbe0`
- `0x18003ff0c`
- `0x1800498e0`
- `0x180049c78`

## callees

- `0x180041100`
- `0x1800472ac`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180041149`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180041149`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180041125`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180041125`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041114`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041114`

## string_xrefs

- `0x180041142`: `ntdll.dll`

## pseudocode

```c

```
