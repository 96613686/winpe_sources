# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180021290`
- end: `0x180021326`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180020ce0`
- `0x1800210cc`
- `0x1800213fc`
- `0x180021538`
- `0x18002da64`
- `0x180036654`

## callees

- `0x180020504`
- `0x180021290`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800212d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800212d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800212b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800212b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800212a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800212a4`

## string_xrefs

- `0x1800212d2`: `ntdll.dll`

## pseudocode

```c

```
