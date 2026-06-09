# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007388`
- end: `0x18000741e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000678c`
- `0x180007170`
- `0x180007614`
- `0x180007750`
- `0x1800150e8`
- `0x18001af04`

## callees

- `0x180005440`
- `0x180007388`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800073d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800073d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000739c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000739c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800073ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800073ad`

## string_xrefs

- `0x1800073ca`: `ntdll.dll`

## pseudocode

```c

```
