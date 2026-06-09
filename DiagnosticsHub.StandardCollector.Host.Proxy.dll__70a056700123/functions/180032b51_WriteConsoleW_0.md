# WriteConsoleW_0

- ea: `0x180032b51`
- end: `0x180032b57`
- name: `WriteConsoleW_0`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE hConsoleOutput, const void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!WriteConsoleW` at `0x180032b51`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall WriteConsoleW_0(
        HANDLE hConsoleOutput,
        const void *lpBuffer,
        DWORD nNumberOfCharsToWrite,
        LPDWORD lpNumberOfCharsWritten,
        LPVOID lpReserved)
{
  return WriteConsoleW(hConsoleOutput, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, lpReserved);
}

```

## disassembly

```asm
0x180032b51  jmp     cs:__imp_WriteConsoleW
```
