# MsiViewGetColumnInfo

- ea: `0x10020f9e`
- end: `0x10020fa4`
- name: `MsiViewGetColumnInfo`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hView, MSICOLINFO eColumnInfo, MSIHANDLE *phRecord)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1000dba2`

## import_xrefs

- `msi!__imp_MsiViewGetColumnInfo` at `0x10020f9e`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiViewGetColumnInfo(MSIHANDLE hView, MSICOLINFO eColumnInfo, MSIHANDLE *phRecord)
{
  return __imp_MsiViewGetColumnInfo(hView, eColumnInfo, phRecord);
}

```

## disassembly

```asm
0x10020f9e  jmp     ds:__imp_MsiViewGetColumnInfo
```
