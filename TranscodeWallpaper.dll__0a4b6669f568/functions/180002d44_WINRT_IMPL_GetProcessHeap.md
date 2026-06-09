# WINRT_IMPL_GetProcessHeap

- ea: `0x180002d44`
- end: `0x180002d4a`
- name: `WINRT_IMPL_GetProcessHeap`
- size: `6`
- prototype: `HANDLE __stdcall()`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180006a74`
- `0x180006cc4`
- `0x18000c8a4`
- `0x18000e257`
- `0x18000e4d4`
- `0x18000e927`
- `0x18000ea20`
- `0x18000eb19`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d44`

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
0x180002d44  jmp     cs:__imp_GetProcessHeap
```
