# GetFullPathNameA_0

- ea: `0x180078b70`
- end: `0x180078b76`
- name: `GetFullPathNameA_0`
- size: `6`
- prototype: `DWORD __stdcall(LPCSTR lpFileName, DWORD nBufferLength, LPSTR lpBuffer, LPSTR *lpFilePart)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x180078b70`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall GetFullPathNameA_0(LPCSTR lpFileName, DWORD nBufferLength, LPSTR lpBuffer, LPSTR *lpFilePart)
{
  return GetFullPathNameA(lpFileName, nBufferLength, lpBuffer, lpFilePart);
}

```

## disassembly

```asm
0x180078b70  jmp     cs:__imp_GetFullPathNameA
```
