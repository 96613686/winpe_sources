# MsiProcessMessage

- ea: `0x10020fe0`
- end: `0x10020fe6`
- name: `MsiProcessMessage`
- size: `6`
- prototype: `int __stdcall(MSIHANDLE hInstall, INSTALLMESSAGE eMessageType, MSIHANDLE hRecord)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1000ee2a`

## import_xrefs

- `msi!__imp_MsiProcessMessage` at `0x10020fe0`

## pseudocode

```c
// attributes: thunk
int __stdcall MsiProcessMessage(MSIHANDLE hInstall, INSTALLMESSAGE eMessageType, MSIHANDLE hRecord)
{
  return __imp_MsiProcessMessage(hInstall, eMessageType, hRecord);
}

```

## disassembly

```asm
0x10020fe0  jmp     ds:__imp_MsiProcessMessage
```
