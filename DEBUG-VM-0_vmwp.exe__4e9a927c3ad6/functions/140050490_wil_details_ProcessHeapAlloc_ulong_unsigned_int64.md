# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140050490`
- end: `0x140050547`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14004ddec`
- `0x1400599d4`
- `0x140137330`
- `0x140137468`
- `0x1401381a4`
- `0x140138650`

## callees

- `0x140050490`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400504e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400504e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140050532`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140050532`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400504bb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400504bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400504a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400504a4`

## string_xrefs

- `0x1400504de`: `ntdll.dll`

## pseudocode

```c

```
