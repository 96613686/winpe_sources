# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800206a0`
- end: `0x180020741`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `161`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001f4c4`
- `0x1800205fc`
- `0x1800683c0`
- `0x1800759b0`
- `0x180075ae0`
- `0x18007693c`
- `0x180076cd4`

## callees

- `0x1800206a0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020732`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020732`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020708`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020708`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800206c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800206c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800206b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800206b4`

## string_xrefs

- `0x180020701`: `ntdll.dll`

## pseudocode

```c

```
