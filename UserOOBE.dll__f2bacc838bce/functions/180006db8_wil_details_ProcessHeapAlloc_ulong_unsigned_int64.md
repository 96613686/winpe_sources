# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006db8`
- end: `0x180006e4e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000611c`
- `0x180006b2c`
- `0x1800071e0`
- `0x180007578`
- `0x18000c3dc`
- `0x18000e480`

## callees

- `0x180004aec`
- `0x180006db8`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006e01`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006e01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006dcc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006dcc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006ddd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006ddd`

## string_xrefs

- `0x180006dfa`: `ntdll.dll`

## pseudocode

```c

```
