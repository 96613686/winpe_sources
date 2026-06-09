# GetCurrentThread_0

- ea: `0x180032ceb`
- end: `0x180032cf1`
- name: `GetCurrentThread_0`
- size: `6`
- prototype: `HANDLE __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180032ceb`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall GetCurrentThread_0()
{
  return GetCurrentThread();
}

```

## disassembly

```asm
0x180032ceb  jmp     cs:__imp_GetCurrentThread
```
