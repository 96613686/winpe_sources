# MsiSetPropertyW

- ea: `0x10020fc2`
- end: `0x10020fc8`
- name: `MsiSetPropertyW`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hInstall, LPCWSTR szName, LPCWSTR szValue)`
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1000e070`
- `0x1000f00c`
- `0x1000f0b5`

## import_xrefs

- `msi!__imp_MsiSetPropertyW` at `0x10020fc2`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiSetPropertyW(MSIHANDLE hInstall, LPCWSTR szName, LPCWSTR szValue)
{
  return __imp_MsiSetPropertyW(hInstall, szName, szValue);
}

```

## disassembly

```asm
0x10020fc2  jmp     ds:__imp_MsiSetPropertyW
```
