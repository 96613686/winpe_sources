# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180009664`
- end: `0x180009702`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007818`
- `0x180008000`
- `0x1800085d0`
- `0x180009b44`
- `0x180017ba4`
- `0x1800187b4`

## callees

- `0x180009664`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800096c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800096c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800096ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800096ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009689`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009689`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009678`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009678`

## string_xrefs

- `0x1800096a6`: `ntdll.dll`

## pseudocode

```c

```
