# CreateFileMappingW_0

- ea: `0x1800458e0`
- end: `0x1800458e6`
- name: `CreateFileMappingW_0`
- size: `6`
- prototype: `HANDLE __stdcall(HANDLE hFile, LPSECURITY_ATTRIBUTES lpFileMappingAttributes, DWORD flProtect, DWORD dwMaximumSizeHigh, DWORD dwMaximumSizeLow, LPCWSTR lpName)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, installer_update, broker_com_uri`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800458e0`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall CreateFileMappingW_0(
        HANDLE hFile,
        LPSECURITY_ATTRIBUTES lpFileMappingAttributes,
        DWORD flProtect,
        DWORD dwMaximumSizeHigh,
        DWORD dwMaximumSizeLow,
        LPCWSTR lpName)
{
  return CreateFileMappingW(hFile, lpFileMappingAttributes, flProtect, dwMaximumSizeHigh, dwMaximumSizeLow, lpName);
}

```

## disassembly

```asm
0x1800458e0  jmp     cs:__imp_CreateFileMappingW
```
