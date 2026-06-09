# MsiDatabaseGetPrimaryKeysW

- ea: `0x10020fa4`
- end: `0x10020faa`
- name: `MsiDatabaseGetPrimaryKeysW`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hDatabase, LPCWSTR szTableName, MSIHANDLE *phRecord)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1000f18d`

## import_xrefs

- `msi!__imp_MsiDatabaseGetPrimaryKeysW` at `0x10020fa4`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiDatabaseGetPrimaryKeysW(MSIHANDLE hDatabase, LPCWSTR szTableName, MSIHANDLE *phRecord)
{
  return __imp_MsiDatabaseGetPrimaryKeysW(hDatabase, szTableName, phRecord);
}

```

## disassembly

```asm
0x10020fa4  jmp     ds:__imp_MsiDatabaseGetPrimaryKeysW
```
