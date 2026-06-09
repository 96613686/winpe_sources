# WriteProcessMemory_0

- ea: `0x1800396fd`
- end: `0x180039703`
- name: `WriteProcessMemory_0`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE hProcess, LPVOID lpBaseAddress, LPCVOID lpBuffer, SIZE_T nSize, SIZE_T *lpNumberOfBytesWritten)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180030b30`

## import_xrefs

- `KERNEL32!WriteProcessMemory` at `0x1800396fd`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall WriteProcessMemory_0(
        HANDLE hProcess,
        LPVOID lpBaseAddress,
        LPCVOID lpBuffer,
        SIZE_T nSize,
        SIZE_T *lpNumberOfBytesWritten)
{
  return WriteProcessMemory(hProcess, lpBaseAddress, lpBuffer, nSize, lpNumberOfBytesWritten);
}

```

## disassembly

```asm
0x1800396fd  jmp     cs:__imp_WriteProcessMemory
```
