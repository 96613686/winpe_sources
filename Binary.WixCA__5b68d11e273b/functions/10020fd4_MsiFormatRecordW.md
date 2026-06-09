# MsiFormatRecordW

- ea: `0x10020fd4`
- end: `0x10020fda`
- name: `MsiFormatRecordW`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hInstall, MSIHANDLE hRecord, LPWSTR szResultBuf, LPDWORD pcchResultBuf)`
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1000e439`
- `0x1000e78c`

## import_xrefs

- `msi!__imp_MsiFormatRecordW` at `0x10020fd4`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiFormatRecordW(MSIHANDLE hInstall, MSIHANDLE hRecord, LPWSTR szResultBuf, LPDWORD pcchResultBuf)
{
  return __imp_MsiFormatRecordW(hInstall, hRecord, szResultBuf, pcchResultBuf);
}

```

## disassembly

```asm
0x10020fd4  jmp     ds:__imp_MsiFormatRecordW
```
