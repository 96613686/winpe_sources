# MsiDatabaseOpenViewW

- ea: `0x10020f80`
- end: `0x10020f86`
- name: `MsiDatabaseOpenViewW`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hDatabase, LPCWSTR szQuery, MSIHANDLE *phView)`
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1000ed03`
- `0x1000edb9`

## import_xrefs

- `msi!__imp_MsiDatabaseOpenViewW` at `0x10020f80`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiDatabaseOpenViewW(MSIHANDLE hDatabase, LPCWSTR szQuery, MSIHANDLE *phView)
{
  return __imp_MsiDatabaseOpenViewW(hDatabase, szQuery, phView);
}

```

## disassembly

```asm
0x10020f80  jmp     ds:__imp_MsiDatabaseOpenViewW
```
