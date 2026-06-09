# GetCurrentThreadId_0

- ea: `0x1800035dc`
- end: `0x1800035e2`
- name: `GetCurrentThreadId_0`
- size: `6`
- prototype: `DWORD __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800035dc`

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
0x1800035dc  jmp     cs:__imp_GetCurrentThreadId
```
