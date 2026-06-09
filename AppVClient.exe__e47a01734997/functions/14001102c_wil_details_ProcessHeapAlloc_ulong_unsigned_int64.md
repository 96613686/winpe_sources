# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14001102c`
- end: `0x1400110ca`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140009d54`
- `0x14000c410`
- `0x140012534`
- `0x14005f364`
- `0x1400632e4`

## callees

- `0x14001102c`
- `0x14006a010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140011040`
- `KERNEL32!GetProcessHeap` at `0x140011040`
- `KERNEL32!GetModuleHandleW` at `0x140011075`
- `KERNEL32!GetModuleHandleW` at `0x140011075`
- `KERNEL32!GetProcAddress` at `0x14001108a`
- `KERNEL32!GetProcAddress` at `0x14001108a`
- `KERNEL32!HeapAlloc` at `0x140011051`
- `KERNEL32!HeapAlloc` at `0x140011051`

## string_xrefs

- `0x14001106e`: `ntdll.dll`

## pseudocode

```c

```
