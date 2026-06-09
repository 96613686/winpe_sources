# MsiGetMode

- ea: `0x10009974`
- end: `0x1000997a`
- name: `MsiGetMode`
- size: `6`
- prototype: `BOOL __stdcall(MSIHANDLE hInstall, MSIRUNMODE eRunMode)`
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x10002fe3`
- `0x10006e43`

## import_xrefs

- `msi!__imp_MsiGetMode` at `0x10009974`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall MsiGetMode(MSIHANDLE hInstall, MSIRUNMODE eRunMode)
{
  return __imp_MsiGetMode(hInstall, eRunMode);
}

```

## disassembly

```asm
0x10009974  jmp     ds:__imp_MsiGetMode
```
