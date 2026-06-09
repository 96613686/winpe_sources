# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800317a0`
- end: `0x18003183e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180032538`
- `0x180051640`
- `0x180061824`
- `0x180062010`
- `0x1800623a8`
- `0x180062b48`

## callees

- `0x1800317a0`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800317fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800317fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800317e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800317e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800317b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800317b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800317c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800317c5`

## string_xrefs

- `0x1800317e2`: `ntdll.dll`

## pseudocode

```c

```
