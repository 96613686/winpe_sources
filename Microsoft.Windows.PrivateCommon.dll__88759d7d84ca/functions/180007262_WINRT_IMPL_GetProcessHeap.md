# WINRT_IMPL_GetProcessHeap

- ea: `0x180007262`
- end: `0x180007268`
- name: `WINRT_IMPL_GetProcessHeap`
- size: `6`
- prototype: `HANDLE __stdcall()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800012f0`
- `0x180001530`
- `0x1800052a0`
- `0x180006ae0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180007262`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall WINRT_IMPL_GetProcessHeap()
{
  return GetProcessHeap();
}

```

## disassembly

```asm
0x180007262  jmp     cs:__imp_GetProcessHeap
```
