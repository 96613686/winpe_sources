# MsiViewGetErrorW

- ea: `0x10020f86`
- end: `0x10020f8c`
- name: `MsiViewGetErrorW`
- size: `6`
- prototype: `MSIDBERROR __stdcall(MSIHANDLE hView, LPWSTR szColumnNameBuffer, LPDWORD pcchBuf)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1000dba2`

## import_xrefs

- `msi!__imp_MsiViewGetErrorW` at `0x10020f86`

## pseudocode

```c
// attributes: thunk
MSIDBERROR __stdcall MsiViewGetErrorW(MSIHANDLE hView, LPWSTR szColumnNameBuffer, LPDWORD pcchBuf)
{
  return __imp_MsiViewGetErrorW(hView, szColumnNameBuffer, pcchBuf);
}

```

## disassembly

```asm
0x10020f86  jmp     ds:__imp_MsiViewGetErrorW
```
