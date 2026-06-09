# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000f298`
- end: `0x18000f32e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000b60c`
- `0x18000b770`
- `0x18000f534`
- `0x18000f6ac`
- `0x180027fa4`

## callees

- `0x18000d63c`
- `0x18000f298`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f2e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f2e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f2bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f2bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f2ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f2ac`

## string_xrefs

- `0x18000f2da`: `ntdll.dll`

## pseudocode

```c

```
