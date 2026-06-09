# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002d228`
- end: `0x18002d2be`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002ccfc`
- `0x18002ce5c`
- `0x18002f170`
- `0x18002f5f8`
- `0x180030824`

## callees

- `0x1800281b4`
- `0x18002d228`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d24d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d24d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d23c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d23c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d271`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d271`

## string_xrefs

- `0x18002d26a`: `ntdll.dll`

## pseudocode

```c

```
