# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800b3c94`
- end: `0x1800b3d32`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800c1310`
- `0x1800c5f64`
- `0x1800c608c`
- `0x1800c7110`
- `0x1800c7598`

## callees

- `0x1800b3c94`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b3cf2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b3cf2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b3cdd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b3cdd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b3ca8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b3ca8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b3cb9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b3cb9`

## string_xrefs

- `0x1800b3cd6`: `ntdll.dll`

## pseudocode

```c

```
