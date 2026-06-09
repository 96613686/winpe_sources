# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140010764`
- end: `0x14001080d`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000f340`
- `0x140010100`
- `0x140010264`
- `0x140011874`
- `0x140011d20`
- `0x140013444`

## callees

- `0x14000cdbc`
- `0x140010764`
- `0x1401b9010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400107b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400107b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010778`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010778`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001078f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001078f`

## string_xrefs

- `0x1400107b2`: `ntdll.dll`

## pseudocode

```c

```
