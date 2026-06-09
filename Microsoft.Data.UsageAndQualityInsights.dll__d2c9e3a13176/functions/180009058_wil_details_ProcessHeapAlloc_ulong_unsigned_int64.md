# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180009058`
- end: `0x1800090f6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006c68`
- `0x180007048`
- `0x180007d50`
- `0x180008320`
- `0x18000a984`
- `0x18000c38c`

## callees

- `0x180009058`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800090a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800090a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800090b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800090b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000907d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000907d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000906c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000906c`

## string_xrefs

- `0x18000909a`: `ntdll.dll`

## pseudocode

```c

```
