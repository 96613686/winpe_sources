# WriteFile_0

- ea: `0x140002b60`
- end: `0x140002b66`
- name: `WriteFile_0`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, LPDWORD lpNumberOfBytesWritten, LPOVERLAPPED lpOverlapped)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140002b60`

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
0x140002b60  jmp     cs:__imp_WriteFile
```
