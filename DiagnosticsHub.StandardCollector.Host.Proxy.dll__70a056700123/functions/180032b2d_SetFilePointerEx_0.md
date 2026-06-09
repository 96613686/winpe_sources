# SetFilePointerEx_0

- ea: `0x180032b2d`
- end: `0x180032b33`
- name: `SetFilePointerEx_0`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE hFile, LARGE_INTEGER liDistanceToMove, PLARGE_INTEGER lpNewFilePointer, DWORD dwMoveMethod)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x180032b2d`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall SetFilePointerEx_0(
        HANDLE hFile,
        LARGE_INTEGER liDistanceToMove,
        PLARGE_INTEGER lpNewFilePointer,
        DWORD dwMoveMethod)
{
  return SetFilePointerEx(hFile, liDistanceToMove, lpNewFilePointer, dwMoveMethod);
}

```

## disassembly

```asm
0x180032b2d  jmp     cs:__imp_SetFilePointerEx
```
