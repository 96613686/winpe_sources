# GetCurrentThread_0

- ea: `0x180032a07`
- end: `0x180032a0d`
- name: `GetCurrentThread_0`
- size: `6`
- prototype: `HANDLE __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180032a07`

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
0x180032a07  jmp     cs:__imp_GetCurrentThread
```
