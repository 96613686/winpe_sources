# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800067b8`
- end: `0x18000684e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006554`
- `0x180006a60`
- `0x180006df8`
- `0x180012ba4`
- `0x1800143ec`

## callees

- `0x18000446c`
- `0x1800067b8`
- `0x18013e010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180006801`
- `KERNEL32!GetModuleHandleW` at `0x180006801`
- `KERNEL32!HeapAlloc` at `0x1800067dd`
- `KERNEL32!HeapAlloc` at `0x1800067dd`
- `KERNEL32!GetProcessHeap` at `0x1800067cc`
- `KERNEL32!GetProcessHeap` at `0x1800067cc`

## string_xrefs

- `0x1800067fa`: `ntdll.dll`

## pseudocode

```c

```
