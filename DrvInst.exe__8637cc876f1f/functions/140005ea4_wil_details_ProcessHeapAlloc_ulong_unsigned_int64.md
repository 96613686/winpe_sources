# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140005ea4`
- end: `0x140005f42`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140005950`
- `0x140005aa4`
- `0x140006c44`
- `0x140006ea8`
- `0x140007f90`

## callees

- `0x140005ea4`
- `0x140047010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005eed`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005eed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005f02`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140005f02`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005ec9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005ec9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005eb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005eb8`

## string_xrefs

- `0x140005ee6`: `ntdll.dll`

## pseudocode

```c

```
