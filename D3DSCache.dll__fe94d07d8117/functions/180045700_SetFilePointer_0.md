# SetFilePointer_0

- ea: `0x180045700`
- end: `0x180045706`
- name: `SetFilePointer_0`
- size: `6`
- prototype: `DWORD __stdcall(HANDLE hFile, LONG lDistanceToMove, PLONG lpDistanceToMoveHigh, DWORD dwMoveMethod)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180045700`

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
0x180045700  jmp     cs:__imp_SetFilePointer
```
