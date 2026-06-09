# MsiSetMode

- ea: `0x10009956`
- end: `0x1000995c`
- name: `MsiSetMode`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hInstall, MSIRUNMODE eRunMode, BOOL fState)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x100011ab`

## import_xrefs

- `msi!__imp_MsiSetMode` at `0x10009956`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiSetMode(MSIHANDLE hInstall, MSIRUNMODE eRunMode, BOOL fState)
{
  return __imp_MsiSetMode(hInstall, eRunMode, fState);
}

```

## disassembly

```asm
0x10009956  jmp     ds:__imp_MsiSetMode
```
