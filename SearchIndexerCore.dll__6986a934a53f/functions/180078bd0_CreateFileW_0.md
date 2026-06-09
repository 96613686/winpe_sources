# CreateFileW_0

- ea: `0x180078bd0`
- end: `0x180078bd6`
- name: `CreateFileW_0`
- size: `6`
- prototype: `HANDLE __stdcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, LPSECURITY_ATTRIBUTES lpSecurityAttributes, DWORD dwCreationDisposition, DWORD dwFlagsAndAttributes, HANDLE hTemplateFile)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180078bd0`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall CreateFileW_0(
        LPCWSTR lpFileName,
        DWORD dwDesiredAccess,
        DWORD dwShareMode,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes,
        HANDLE hTemplateFile)
{
  return CreateFileW(
           lpFileName,
           dwDesiredAccess,
           dwShareMode,
           lpSecurityAttributes,
           dwCreationDisposition,
           dwFlagsAndAttributes,
           hTemplateFile);
}

```

## disassembly

```asm
0x180078bd0  jmp     cs:__imp_CreateFileW
```
