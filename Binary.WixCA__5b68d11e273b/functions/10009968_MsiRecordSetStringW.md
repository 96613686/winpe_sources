# MsiRecordSetStringW

- ea: `0x10009968`
- end: `0x1000996e`
- name: `MsiRecordSetStringW`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hRecord, UINT iField, LPCWSTR szValue)`
- caller_count: `6`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x100012eb`
- `0x10003e9c`
- `0x1000dba2`
- `0x1000e13e`
- `0x1000e439`
- `0x1000f126`

## import_xrefs

- `msi!__imp_MsiRecordSetStringW` at `0x10009968`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiRecordSetStringW(MSIHANDLE hRecord, UINT iField, LPCWSTR szValue)
{
  return __imp_MsiRecordSetStringW(hRecord, iField, szValue);
}

```

## disassembly

```asm
0x10009968  jmp     ds:__imp_MsiRecordSetStringW
```
