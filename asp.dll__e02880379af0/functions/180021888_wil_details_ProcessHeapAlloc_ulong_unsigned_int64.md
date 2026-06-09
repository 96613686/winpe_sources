# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180021888`
- end: `0x180021926`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180021480`
- `0x1800215a8`
- `0x1800226e4`
- `0x180022910`
- `0x1800236c4`

## callees

- `0x180021888`
- `0x180064010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18002189c`
- `KERNEL32!GetProcessHeap` at `0x18002189c`
- `KERNEL32!HeapAlloc` at `0x1800218ad`
- `KERNEL32!HeapAlloc` at `0x1800218ad`
- `KERNEL32!GetModuleHandleW` at `0x1800218d1`
- `KERNEL32!GetModuleHandleW` at `0x1800218d1`
- `KERNEL32!GetProcAddress` at `0x1800218e6`
- `KERNEL32!GetProcAddress` at `0x1800218e6`

## string_xrefs

- `0x1800218ca`: `ntdll.dll`

## pseudocode

```c

```
