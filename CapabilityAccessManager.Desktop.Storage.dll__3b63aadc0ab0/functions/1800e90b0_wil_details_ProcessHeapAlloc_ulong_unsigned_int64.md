# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800e90b0`
- end: `0x1800e914e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800e6c08`
- `0x1800e6fe4`
- `0x1800e7d20`
- `0x1800e8310`
- `0x1800eace4`
- `0x1800ec730`

## callees

- `0x1800e90b0`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e910e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e910e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800e90f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800e90f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e90c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e90c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e90d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e90d5`

## string_xrefs

- `0x1800e90f2`: `ntdll.dll`

## pseudocode

```c

```
