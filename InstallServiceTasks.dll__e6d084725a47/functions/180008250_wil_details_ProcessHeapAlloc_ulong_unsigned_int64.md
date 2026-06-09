# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008250`
- end: `0x1800082e6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007c70`
- `0x180007dd4`
- `0x1800091d0`
- `0x180009660`
- `0x18000a85c`

## callees

- `0x180004d14`
- `0x180008250`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008299`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008299`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008275`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008275`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008264`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008264`

## string_xrefs

- `0x180008292`: `ntdll.dll`

## pseudocode

```c

```
