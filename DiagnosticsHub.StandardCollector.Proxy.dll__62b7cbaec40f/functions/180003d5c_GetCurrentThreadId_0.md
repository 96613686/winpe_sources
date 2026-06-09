# GetCurrentThreadId_0

- ea: `0x180003d5c`
- end: `0x180003d62`
- name: `GetCurrentThreadId_0`
- size: `6`
- prototype: `DWORD __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180003d5c`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall GetCurrentThreadId_0()
{
  return GetCurrentThreadId();
}

```

## disassembly

```asm
0x180003d5c  jmp     cs:__imp_GetCurrentThreadId
```
