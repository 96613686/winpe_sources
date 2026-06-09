# WINRT_IMPL_GetProcessHeap

- ea: `0x180002eb8`
- end: `0x180002ebe`
- name: `WINRT_IMPL_GetProcessHeap`
- size: `6`
- prototype: `HANDLE __stdcall()`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180005314`
- `0x18000ed6c`
- `0x18000f09c`
- `0x180010858`
- `0x180010ad5`
- `0x180010e6d`
- `0x180010f66`
- `0x18001105f`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002eb8`

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
0x180002eb8  jmp     cs:__imp_GetProcessHeap
```
