# WINRT_IMPL_GetProcessHeap

- ea: `0x180003b1c`
- end: `0x180003b22`
- name: `WINRT_IMPL_GetProcessHeap`
- size: `6`
- prototype: `HANDLE __stdcall()`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c974`
- `0x18000d038`
- `0x18000d450`
- `0x18000d4d4`
- `0x18000e220`
- `0x18000e950`
- `0x18000f9dc`
- `0x180010e7c`
- `0x1800116c4`
- `0x180012791`
- `0x180012895`
- `0x180012999`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b1c`

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
0x180003b1c  jmp     cs:__imp_GetProcessHeap
```
