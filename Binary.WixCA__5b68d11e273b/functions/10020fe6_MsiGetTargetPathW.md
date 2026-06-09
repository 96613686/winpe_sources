# MsiGetTargetPathW

- ea: `0x10020fe6`
- end: `0x10020fec`
- name: `MsiGetTargetPathW`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hInstall, LPCWSTR szFolder, LPWSTR szPathBuf, LPDWORD pcchPathBuf)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1000eafc`

## import_xrefs

- `msi!__imp_MsiGetTargetPathW` at `0x10020fe6`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiGetTargetPathW(MSIHANDLE hInstall, LPCWSTR szFolder, LPWSTR szPathBuf, LPDWORD pcchPathBuf)
{
  return __imp_MsiGetTargetPathW(hInstall, szFolder, szPathBuf, pcchPathBuf);
}

```

## disassembly

```asm
0x10020fe6  jmp     ds:__imp_MsiGetTargetPathW
```
