# WINRT_IMPL_GetProcessHeap

- ea: `0x180002070`
- end: `0x180002076`
- name: `WINRT_IMPL_GetProcessHeap`
- size: `6`
- prototype: `HANDLE __stdcall()`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x18000614c`
- `0x180007438`
- `0x180008124`
- `0x180008190`
- `0x18000972c`
- `0x18000bb6e`
- `0x18000bc67`
- `0x18000bd60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002070`

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
0x180002070  jmp     cs:__imp_GetProcessHeap
```
