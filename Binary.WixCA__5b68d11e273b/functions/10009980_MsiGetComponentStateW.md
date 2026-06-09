# MsiGetComponentStateW

- ea: `0x10009980`
- end: `0x10009986`
- name: `MsiGetComponentStateW`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hInstall, LPCWSTR szComponent, INSTALLSTATE *piInstalled, INSTALLSTATE *piAction)`
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10004da5`
- `0x10006208`
- `0x1000722e`
- `0x100086c2`
- `0x1000e355`

## import_xrefs

- `msi!__imp_MsiGetComponentStateW` at `0x10009980`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiGetComponentStateW(
        MSIHANDLE hInstall,
        LPCWSTR szComponent,
        INSTALLSTATE *piInstalled,
        INSTALLSTATE *piAction)
{
  return __imp_MsiGetComponentStateW(hInstall, szComponent, piInstalled, piAction);
}

```

## disassembly

```asm
0x10009980  jmp     ds:__imp_MsiGetComponentStateW
```
