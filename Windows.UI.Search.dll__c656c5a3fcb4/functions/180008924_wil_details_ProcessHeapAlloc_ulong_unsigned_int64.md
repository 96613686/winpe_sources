# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008924`
- end: `0x1800089ba`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180008220`
- `0x180008384`
- `0x180009e10`
- `0x18000a294`
- `0x18000c0d4`

## callees

- `0x1800045f8`
- `0x180008924`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000896d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000896d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008938`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008938`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008949`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008949`

## string_xrefs

- `0x180008966`: `ntdll.dll`

## pseudocode

```c

```
