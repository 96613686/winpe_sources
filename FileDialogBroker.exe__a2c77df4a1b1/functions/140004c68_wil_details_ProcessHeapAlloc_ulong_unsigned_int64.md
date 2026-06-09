# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140004c68`
- end: `0x140004cfe`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140003fec`
- `0x1400049e8`
- `0x1400050ec`
- `0x140005484`

## callees

- `0x140002a70`
- `0x140004c68`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004cb1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140004cb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004c7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004c7c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140004c8d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140004c8d`

## string_xrefs

- `0x140004caa`: `ntdll.dll`

## pseudocode

```c

```
