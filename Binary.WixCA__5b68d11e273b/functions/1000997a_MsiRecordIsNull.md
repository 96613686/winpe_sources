# MsiRecordIsNull

- ea: `0x1000997a`
- end: `0x10009980`
- name: `MsiRecordIsNull`
- size: `6`
- prototype: `BOOL __stdcall(MSIHANDLE hRecord, UINT iField)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x100034ad`

## import_xrefs

- `msi!__imp_MsiRecordIsNull` at `0x1000997a`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall MsiRecordIsNull(MSIHANDLE hRecord, UINT iField)
{
  return __imp_MsiRecordIsNull(hRecord, iField);
}

```

## disassembly

```asm
0x1000997a  jmp     ds:__imp_MsiRecordIsNull
```
