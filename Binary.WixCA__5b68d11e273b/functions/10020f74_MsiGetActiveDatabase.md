# MsiGetActiveDatabase

- ea: `0x10020f74`
- end: `0x10020f7a`
- name: `MsiGetActiveDatabase`
- size: `6`
- prototype: `MSIHANDLE __stdcall(MSIHANDLE hInstall)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1000d51f`

## import_xrefs

- `msi!__imp_MsiGetActiveDatabase` at `0x10020f74`

## pseudocode

```c
// attributes: thunk
MSIHANDLE __stdcall MsiGetActiveDatabase(MSIHANDLE hInstall)
{
  return __imp_MsiGetActiveDatabase(hInstall);
}

```

## disassembly

```asm
0x10020f74  jmp     ds:__imp_MsiGetActiveDatabase
```
