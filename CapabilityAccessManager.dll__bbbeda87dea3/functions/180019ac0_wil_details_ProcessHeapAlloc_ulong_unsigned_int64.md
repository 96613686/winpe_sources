# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180019ac0`
- end: `0x180019b56`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800185cc`
- `0x1800194d8`
- `0x18001963c`
- `0x18001ac94`
- `0x18001b124`
- `0x18001c674`

## callees

- `0x1800159f4`
- `0x180019ac0`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019b09`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019b09`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019ae5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019ae5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ad4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ad4`

## string_xrefs

- `0x180019b02`: `ntdll.dll`

## pseudocode

```c

```
