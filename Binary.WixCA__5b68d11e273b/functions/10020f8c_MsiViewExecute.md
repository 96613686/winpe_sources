# MsiViewExecute

- ea: `0x10020f8c`
- end: `0x10020f92`
- name: `MsiViewExecute`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hView, MSIHANDLE hRecord)`
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1000e250`
- `0x1000ed03`

## import_xrefs

- `msi!__imp_MsiViewExecute` at `0x10020f8c`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiViewExecute(MSIHANDLE hView, MSIHANDLE hRecord)
{
  return __imp_MsiViewExecute(hView, hRecord);
}

```

## disassembly

```asm
0x10020f8c  jmp     ds:__imp_MsiViewExecute
```
