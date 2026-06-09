# MsiCreateRecord

- ea: `0x10009962`
- end: `0x10009968`
- name: `MsiCreateRecord`
- size: `6`
- prototype: `MSIHANDLE __stdcall(UINT cParams)`
- caller_count: `9`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x100012eb`
- `0x10003e9c`
- `0x100044d9`
- `0x1000d9ab`
- `0x1000dba2`
- `0x1000e13e`
- `0x1000e439`
- `0x1000e78c`
- `0x1000ee5c`

## import_xrefs

- `msi!__imp_MsiCreateRecord` at `0x10009962`

## pseudocode

```c
// attributes: thunk
MSIHANDLE __stdcall MsiCreateRecord(UINT cParams)
{
  return __imp_MsiCreateRecord(cParams);
}

```

## disassembly

```asm
0x10009962  jmp     ds:__imp_MsiCreateRecord
```
