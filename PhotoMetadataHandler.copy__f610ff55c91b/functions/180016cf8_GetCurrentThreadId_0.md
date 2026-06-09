# GetCurrentThreadId_0

- ea: `0x180016cf8`
- end: `0x180016cfe`
- name: `GetCurrentThreadId_0`
- size: `6`
- prototype: `DWORD __stdcall()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180022224`
- `0x1800233f0`
- `0x1800234a4`
- `0x180023760`
- `0x180023a14`
- `0x180023d50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016cf8`

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
0x180016cf8  jmp     cs:__imp_GetCurrentThreadId
```
