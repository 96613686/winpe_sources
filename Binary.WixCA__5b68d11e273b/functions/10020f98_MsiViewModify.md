# MsiViewModify

- ea: `0x10020f98`
- end: `0x10020f9e`
- name: `MsiViewModify`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hView, MSIMODIFY eModifyMode, MSIHANDLE hRecord)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1000dba2`

## import_xrefs

- `msi!__imp_MsiViewModify` at `0x10020f98`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiViewModify(MSIHANDLE hView, MSIMODIFY eModifyMode, MSIHANDLE hRecord)
{
  return __imp_MsiViewModify(hView, eModifyMode, hRecord);
}

```

## disassembly

```asm
0x10020f98  jmp     ds:__imp_MsiViewModify
```
