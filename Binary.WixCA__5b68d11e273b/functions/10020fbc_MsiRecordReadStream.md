# MsiRecordReadStream

- ea: `0x10020fbc`
- end: `0x10020fc2`
- name: `MsiRecordReadStream`
- size: `6`
- prototype: `UINT __stdcall(MSIHANDLE hRecord, UINT iField, char *szDataBuf, LPDWORD pcbDataBuf)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1000e917`

## import_xrefs

- `msi!__imp_MsiRecordReadStream` at `0x10020fbc`

## pseudocode

```c
// attributes: thunk
UINT __stdcall MsiRecordReadStream(MSIHANDLE hRecord, UINT iField, char *szDataBuf, LPDWORD pcbDataBuf)
{
  return __imp_MsiRecordReadStream(hRecord, iField, szDataBuf, pcbDataBuf);
}

```

## disassembly

```asm
0x10020fbc  jmp     ds:__imp_MsiRecordReadStream
```
