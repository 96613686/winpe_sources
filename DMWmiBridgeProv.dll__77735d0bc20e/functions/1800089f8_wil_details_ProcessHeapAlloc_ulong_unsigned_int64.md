# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800089f8`
- end: `0x180008a8e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180008788`
- `0x180008ecc`
- `0x180009264`

## callees

- `0x180002e80`
- `0x1800089f8`
- `0x18024f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a41`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a41`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008a1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008a1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a0c`

## string_xrefs

- `0x180008a3a`: `ntdll.dll`

## pseudocode

```c

```
