# CreateFileW_0

- ea: `0x180032b45`
- end: `0x180032b4b`
- name: `CreateFileW_0`
- size: `6`
- prototype: `HANDLE __stdcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, LPSECURITY_ATTRIBUTES lpSecurityAttributes, DWORD dwCreationDisposition, DWORD dwFlagsAndAttributes, HANDLE hTemplateFile)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180032b45`

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
0x180032b45  jmp     cs:__imp_CreateFileW
```
