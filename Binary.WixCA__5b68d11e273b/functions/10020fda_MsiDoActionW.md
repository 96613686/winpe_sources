# MsiDoActionW

- ea: `0x10020fda`
- end: `0x10020fe0`
- name: `MsiDoActionW`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hInstall, LPCWSTR szAction)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1000e070`

## import_xrefs

- `msi!__imp_MsiDoActionW` at `0x10020fda`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiDoActionW(MSIHANDLE hInstall, LPCWSTR szAction)
{
  return __imp_MsiDoActionW(hInstall, szAction);
}

```

## disassembly

```asm
0x10020fda  jmp     ds:__imp_MsiDoActionW
```
