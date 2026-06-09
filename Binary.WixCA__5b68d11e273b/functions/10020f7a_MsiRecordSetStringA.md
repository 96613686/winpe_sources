# MsiRecordSetStringA

- ea: `0x10020f7a`
- end: `0x10020f80`
- name: `MsiRecordSetStringA`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hRecord, UINT iField, LPCSTR szValue)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1000d9ab`

## import_xrefs

- `msi!__imp_MsiRecordSetStringA` at `0x10020f7a`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiRecordSetStringA(MSIHANDLE hRecord, UINT iField, LPCSTR szValue)
{
  return __imp_MsiRecordSetStringA(hRecord, iField, szValue);
}

```

## disassembly

```asm
0x10020f7a  jmp     ds:__imp_MsiRecordSetStringA
```
