# WINRT_IMPL_GetProcessHeap

- ea: `0x180002314`
- end: `0x18000231a`
- name: `WINRT_IMPL_GetProcessHeap`
- size: `6`
- prototype: `HANDLE __stdcall()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180004ae8`
- `0x1800057fc`
- `0x180007250`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002314`

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
0x180002314  jmp     cs:__imp_GetProcessHeap
```
