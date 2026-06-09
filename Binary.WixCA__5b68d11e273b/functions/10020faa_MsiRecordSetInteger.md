# MsiRecordSetInteger

- ea: `0x10020faa`
- end: `0x10020fb0`
- name: `MsiRecordSetInteger`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hRecord, UINT iField, int iValue)`
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1000dba2`
- `0x1000e13e`
- `0x1000ee5c`

## import_xrefs

- `msi!__imp_MsiRecordSetInteger` at `0x10020faa`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiRecordSetInteger(MSIHANDLE hRecord, UINT iField, int iValue)
{
  return __imp_MsiRecordSetInteger(hRecord, iField, iValue);
}

```

## disassembly

```asm
0x10020faa  jmp     ds:__imp_MsiRecordSetInteger
```
