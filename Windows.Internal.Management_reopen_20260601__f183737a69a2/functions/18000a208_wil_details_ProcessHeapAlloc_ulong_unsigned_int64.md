# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000a208`
- end: `0x18000a2b1`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180009544`
- `0x180009f7c`
- `0x18000a674`
- `0x18000aa28`
- `0x18001048c`
- `0x1800132c8`

## callees

- `0x180007e08`
- `0x18000a208`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a25d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a25d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a233`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a233`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a21c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a21c`

## string_xrefs

- `0x18000a256`: `ntdll.dll`

## pseudocode

```c

```
