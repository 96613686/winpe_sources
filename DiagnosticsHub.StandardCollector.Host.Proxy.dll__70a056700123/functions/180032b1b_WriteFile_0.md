# WriteFile_0

- ea: `0x180032b1b`
- end: `0x180032b21`
- name: `WriteFile_0`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, LPDWORD lpNumberOfBytesWritten, LPOVERLAPPED lpOverlapped)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180032b1b`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall WriteFile_0(
        HANDLE hFile,
        LPCVOID lpBuffer,
        DWORD nNumberOfBytesToWrite,
        LPDWORD lpNumberOfBytesWritten,
        LPOVERLAPPED lpOverlapped)
{
  return WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, lpNumberOfBytesWritten, lpOverlapped);
}

```

## disassembly

```asm
0x180032b1b  jmp     cs:__imp_WriteFile
```
