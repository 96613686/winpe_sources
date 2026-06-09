# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180041574`
- end: `0x18004162b`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800414a4`
- `0x1800ef010`
- `0x1800ef624`
- `0x1800ef75c`
- `0x1800f0408`
- `0x1800f064c`

## callees

- `0x180041574`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800415e4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800415e4`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800415c9`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800415c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041588`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041588`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004159f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004159f`

## string_xrefs

- `0x1800415c2`: `ntdll.dll`

## pseudocode

```c

```
