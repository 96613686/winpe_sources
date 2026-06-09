# GetCurrentThreadId_0

- ea: `0x180001fa3`
- end: `0x180001fa9`
- name: `GetCurrentThreadId_0`
- size: `6`
- prototype: `DWORD __stdcall()`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800049dc`
- `0x180004d64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001fa3`

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
0x180001fa3  jmp     cs:__imp_GetCurrentThreadId
```
