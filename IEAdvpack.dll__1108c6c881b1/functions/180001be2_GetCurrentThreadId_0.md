# GetCurrentThreadId_0

- ea: `0x180001be2`
- end: `0x180001be8`
- name: `GetCurrentThreadId_0`
- size: `6`
- prototype: `DWORD __stdcall()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800183c8`
- `0x180018f80`
- `0x180019034`
- `0x18001938c`
- `0x1800194cc`
- `0x1800199e0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180001be2`

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
0x180001be2  jmp     cs:__imp_GetCurrentThreadId
```
