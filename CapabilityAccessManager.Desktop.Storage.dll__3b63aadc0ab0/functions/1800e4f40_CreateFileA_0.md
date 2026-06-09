# CreateFileA_0

- ea: `0x1800e4f40`
- end: `0x1800e4f46`
- name: `CreateFileA_0`
- size: `6`
- prototype: `HANDLE __stdcall(LPCSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, LPSECURITY_ATTRIBUTES lpSecurityAttributes, DWORD dwCreationDisposition, DWORD dwFlagsAndAttributes, HANDLE hTemplateFile)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800e4f40`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall CreateFileA_0(
        LPCSTR lpFileName,
        DWORD dwDesiredAccess,
        DWORD dwShareMode,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes,
        HANDLE hTemplateFile)
{
  return CreateFileA(
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
0x1800e4f40  jmp     cs:__imp_CreateFileA
```
