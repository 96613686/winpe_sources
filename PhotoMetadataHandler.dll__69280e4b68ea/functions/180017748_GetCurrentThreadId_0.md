# GetCurrentThreadId_0

- ea: `0x180017748`
- end: `0x18001774e`
- name: `GetCurrentThreadId_0`
- size: `6`
- prototype: `DWORD __stdcall()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180023328`
- `0x180024560`
- `0x180024614`
- `0x1800248d8`
- `0x180024b98`
- `0x180024efc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017748`

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
0x180017748  jmp     cs:__imp_GetCurrentThreadId
```
