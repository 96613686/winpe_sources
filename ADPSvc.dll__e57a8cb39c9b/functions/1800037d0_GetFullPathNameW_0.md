# GetFullPathNameW_0

- ea: `0x1800037d0`
- end: `0x1800037d6`
- name: `GetFullPathNameW_0`
- size: `6`
- prototype: `DWORD __stdcall(LPCWSTR lpFileName, DWORD nBufferLength, LPWSTR lpBuffer, LPWSTR *lpFilePart)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800037d0`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall GetFullPathNameW_0(LPCWSTR lpFileName, DWORD nBufferLength, LPWSTR lpBuffer, LPWSTR *lpFilePart)
{
  return GetFullPathNameW(lpFileName, nBufferLength, lpBuffer, lpFilePart);
}

```

## disassembly

```asm
0x1800037d0  jmp     cs:__imp_GetFullPathNameW
```
