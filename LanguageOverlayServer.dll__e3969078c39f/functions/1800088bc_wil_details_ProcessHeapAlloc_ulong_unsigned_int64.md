# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800088bc`
- end: `0x18000895a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007168`
- `0x180007960`
- `0x180007f30`
- `0x180009174`
- `0x18000cbb8`
- `0x180012cd4`

## callees

- `0x1800088bc`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000891a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000891a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008905`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008905`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800088e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800088e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088d0`

## string_xrefs

- `0x1800088fe`: `ntdll.dll`

## pseudocode

```c

```
