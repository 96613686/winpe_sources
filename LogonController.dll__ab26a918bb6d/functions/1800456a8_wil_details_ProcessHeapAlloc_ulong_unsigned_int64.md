# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800456a8`
- end: `0x180045749`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `161`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b290`
- `0x18000b410`
- `0x18000b89c`
- `0x18003c8c0`
- `0x180064794`
- `0x18006ff90`
- `0x1800705d0`
- `0x18007dbd4`

## callees

- `0x1800456a8`
- `0x18009d010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18004573a`
- `KERNEL32!GetProcAddress` at `0x18004573a`
- `KERNEL32!GetModuleHandleW` at `0x180045710`
- `KERNEL32!GetModuleHandleW` at `0x180045710`
- `KERNEL32!HeapAlloc` at `0x1800456cd`
- `KERNEL32!HeapAlloc` at `0x1800456cd`
- `KERNEL32!GetProcessHeap` at `0x1800456bc`
- `KERNEL32!GetProcessHeap` at `0x1800456bc`

## string_xrefs

- `0x180045709`: `ntdll.dll`

## pseudocode

```c

```
