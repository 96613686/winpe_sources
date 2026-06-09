# MsiRecordGetStringW

- ea: `0x10020fb6`
- end: `0x10020fbc`
- name: `MsiRecordGetStringW`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hRecord, UINT iField, LPWSTR szValueBuf, LPDWORD pcchValueBuf)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1000e9ed`

## import_xrefs

- `msi!__imp_MsiRecordGetStringW` at `0x10020fb6`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiRecordGetStringW(MSIHANDLE hRecord, UINT iField, LPWSTR szValueBuf, LPDWORD pcchValueBuf)
{
  return __imp_MsiRecordGetStringW(hRecord, iField, szValueBuf, pcchValueBuf);
}

```

## disassembly

```asm
0x10020fb6  jmp     ds:__imp_MsiRecordGetStringW
```
