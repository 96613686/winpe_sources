# ReadConsoleW_0

- ea: `0x180032b39`
- end: `0x180032b3f`
- name: `ReadConsoleW_0`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE hConsoleInput, LPVOID lpBuffer, DWORD nNumberOfCharsToRead, LPDWORD lpNumberOfCharsRead, PCONSOLE_READCONSOLE_CONTROL pInputControl)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!ReadConsoleW` at `0x180032b39`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall ReadConsoleW_0(
        HANDLE hConsoleInput,
        LPVOID lpBuffer,
        DWORD nNumberOfCharsToRead,
        LPDWORD lpNumberOfCharsRead,
        PCONSOLE_READCONSOLE_CONTROL pInputControl)
{
  return ReadConsoleW(hConsoleInput, lpBuffer, nNumberOfCharsToRead, lpNumberOfCharsRead, pInputControl);
}

```

## disassembly

```asm
0x180032b39  jmp     cs:__imp_ReadConsoleW
```
