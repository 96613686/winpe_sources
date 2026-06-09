# MsiRecordGetInteger

- ea: `0x10020fb0`
- end: `0x10020fb6`
- name: `MsiRecordGetInteger`
- size: `6`
- prototype: `int __stdcall(MSIHANDLE hRecord, UINT iField)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1000e8e1`

## import_xrefs

- `msi!__imp_MsiRecordGetInteger` at `0x10020fb0`

## pseudocode

```c
// attributes: thunk
int __stdcall MsiRecordGetInteger(MSIHANDLE hRecord, UINT iField)
{
  return __imp_MsiRecordGetInteger(hRecord, iField);
}

```

## disassembly

```asm
0x10020fb0  jmp     ds:__imp_MsiRecordGetInteger
```
