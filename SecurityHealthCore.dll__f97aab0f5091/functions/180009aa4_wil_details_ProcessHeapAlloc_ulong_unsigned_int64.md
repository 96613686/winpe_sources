# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180009aa4`
- end: `0x180009b3a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000952c`
- `0x180009690`
- `0x18000a890`
- `0x18000ad14`
- `0x18000bf0c`

## callees

- `0x1800066d4`
- `0x180009aa4`
- `0x1800e7010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180009ac9`
- `KERNEL32!HeapAlloc` at `0x180009ac9`
- `KERNEL32!GetProcessHeap` at `0x180009ab8`
- `KERNEL32!GetProcessHeap` at `0x180009ab8`
- `KERNEL32!GetModuleHandleW` at `0x180009aed`
- `KERNEL32!GetModuleHandleW` at `0x180009aed`

## string_xrefs

- `0x180009ae6`: `ntdll.dll`

## pseudocode

```c

```
