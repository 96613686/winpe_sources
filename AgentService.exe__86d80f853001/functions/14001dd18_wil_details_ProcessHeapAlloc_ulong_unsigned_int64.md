# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14001dd18`
- end: `0x14001ddb6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001c61c`
- `0x14001ccc0`
- `0x14001e080`

## callees

- `0x14001dd18`
- `0x14009b010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14001dd61`
- `KERNEL32!GetModuleHandleW` at `0x14001dd61`
- `KERNEL32!GetProcessHeap` at `0x14001dd2c`
- `KERNEL32!GetProcessHeap` at `0x14001dd2c`
- `KERNEL32!GetProcAddress` at `0x14001dd76`
- `KERNEL32!GetProcAddress` at `0x14001dd76`
- `KERNEL32!HeapAlloc` at `0x14001dd3d`
- `KERNEL32!HeapAlloc` at `0x14001dd3d`

## string_xrefs

- `0x14001dd5a`: `ntdll.dll`

## pseudocode

```c

```
