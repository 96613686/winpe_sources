# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008dc8`
- end: `0x180008e71`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180008b50`
- `0x1800092cc`
- `0x180009680`

## callees

- `0x180002f00`
- `0x180008dc8`
- `0x18024f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008e1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008e1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008df3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008df3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008ddc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008ddc`

## string_xrefs

- `0x180008e16`: `ntdll.dll`

## pseudocode

```c

```
