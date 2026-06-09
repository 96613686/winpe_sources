# MsiGetPropertyA

- ea: `0x10020fc8`
- end: `0x10020fce`
- name: `MsiGetPropertyA`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hInstall, LPCSTR szName, LPSTR szValueBuf, LPDWORD pcchValueBuf)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1000ec52`

## import_xrefs

- `msi!__imp_MsiGetPropertyA` at `0x10020fc8`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiGetPropertyA(MSIHANDLE hInstall, LPCSTR szName, LPSTR szValueBuf, LPDWORD pcchValueBuf)
{
  return __imp_MsiGetPropertyA(hInstall, szName, szValueBuf, pcchValueBuf);
}

```

## disassembly

```asm
0x10020fc8  jmp     ds:__imp_MsiGetPropertyA
```
