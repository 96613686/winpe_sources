# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001ed5c`
- end: `0x18001edf2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180014e0c`
- `0x180014f70`
- `0x18001e690`
- `0x18001f490`
- `0x18001f828`
- `0x180027d64`

## callees

- `0x18001d1d0`
- `0x18001ed5c`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001eda5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001eda5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ed70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ed70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ed81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ed81`

## string_xrefs

- `0x18001ed9e`: `ntdll.dll`

## pseudocode

```c

```
