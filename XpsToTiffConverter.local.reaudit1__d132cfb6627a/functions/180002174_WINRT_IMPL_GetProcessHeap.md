# WINRT_IMPL_GetProcessHeap

- ea: `0x180002174`
- end: `0x18000217a`
- name: `WINRT_IMPL_GetProcessHeap`
- size: `6`
- prototype: `HANDLE __stdcall()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800030c0`
- `0x180008934`
- `0x1800096f0`
- `0x18000d05c`
- `0x18000d32c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002174`

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
0x180002174  jmp     cs:__imp_GetProcessHeap
```
