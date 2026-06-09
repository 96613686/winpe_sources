# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18003c91c`
- end: `0x18003c9b2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003bb0c`
- `0x180097568`
- `0x180099e78`
- `0x1800b462c`
- `0x1800b4be0`
- `0x1800b4d1c`

## callees

- `0x180039678`
- `0x18003c91c`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003c965`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003c965`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c930`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c930`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c941`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c941`

## string_xrefs

- `0x18003c95e`: `ntdll.dll`

## pseudocode

```c

```
