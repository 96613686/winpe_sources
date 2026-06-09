# WriteFile_0

- ea: `0x1800037e0`
- end: `0x1800037e6`
- name: `WriteFile_0`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, LPDWORD lpNumberOfBytesWritten, LPOVERLAPPED lpOverlapped)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800037e0`

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
0x1800037e0  jmp     cs:__imp_WriteFile
```
