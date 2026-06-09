# WINRT_IMPL_GetProcessHeap

- ea: `0x180002224`
- end: `0x18000222a`
- name: `WINRT_IMPL_GetProcessHeap`
- size: `6`
- prototype: `HANDLE __stdcall()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a88c`
- `0x18000aa9c`
- `0x1800100ed`
- `0x1800103bd`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002224`

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
0x180002224  jmp     cs:__imp_GetProcessHeap
```
