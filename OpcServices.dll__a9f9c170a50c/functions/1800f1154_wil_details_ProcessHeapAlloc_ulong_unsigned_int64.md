# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800f1154`
- end: `0x1800f11f4`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `160`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800f1004`
- `0x1800f14f4`
- `0x1800f188c`

## callees

- `0x1800ef330`
- `0x1800f1154`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800f11a7`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800f11a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f1172`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f1172`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f1183`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f1183`

## string_xrefs

- `0x1800f11a0`: `ntdll.dll`

## pseudocode

```c

```
