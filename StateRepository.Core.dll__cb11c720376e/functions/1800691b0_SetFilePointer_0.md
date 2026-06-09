# SetFilePointer_0

- ea: `0x1800691b0`
- end: `0x1800691b6`
- name: `SetFilePointer_0`
- size: `6`
- prototype: `DWORD __stdcall(HANDLE hFile, LONG lDistanceToMove, PLONG lpDistanceToMoveHigh, DWORD dwMoveMethod)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800691b0`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall SetFilePointer_0(HANDLE hFile, LONG lDistanceToMove, PLONG lpDistanceToMoveHigh, DWORD dwMoveMethod)
{
  return SetFilePointer(hFile, lDistanceToMove, lpDistanceToMoveHigh, dwMoveMethod);
}

```

## disassembly

```asm
0x1800691b0  jmp     cs:__imp_SetFilePointer
```
