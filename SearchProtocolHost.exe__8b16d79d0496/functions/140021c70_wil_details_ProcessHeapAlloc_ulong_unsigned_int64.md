# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140021c70`
- end: `0x140021d10`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `160`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14001d20c`
- `0x140020230`
- `0x140020360`
- `0x14002822c`
- `0x140028894`
- `0x140037ae8`

## callees

- `0x14000865c`
- `0x140021c70`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140021cc3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140021cc3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140021c9f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140021c9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140021c8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140021c8e`

## string_xrefs

- `0x140021cbc`: `ntdll.dll`

## pseudocode

```c

```
