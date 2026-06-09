# MsiGetPropertyW

- ea: `0x10020fce`
- end: `0x10020fd4`
- name: `MsiGetPropertyW`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hInstall, LPCWSTR szName, LPWSTR szValueBuf, LPDWORD pcchValueBuf)`
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1000e5c3`
- `0x1000e662`
- `0x1000ecae`

## import_xrefs

- `msi!__imp_MsiGetPropertyW` at `0x10020fce`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiGetPropertyW(MSIHANDLE hInstall, LPCWSTR szName, LPWSTR szValueBuf, LPDWORD pcchValueBuf)
{
  return __imp_MsiGetPropertyW(hInstall, szName, szValueBuf, pcchValueBuf);
}

```

## disassembly

```asm
0x10020fce  jmp     ds:__imp_MsiGetPropertyW
```
