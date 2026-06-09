# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180071b9c`
- end: `0x180071c32`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180071c38`
- `0x180087ec0`
- `0x1800881e0`
- `0x18008831c`
- `0x180090aa0`

## callees

- `0x180071b9c`
- `0x1800874e8`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180071be5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180071be5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071bb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180071bb0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180071bc1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180071bc1`

## string_xrefs

- `0x180071bde`: `ntdll.dll`

## pseudocode

```c

```
