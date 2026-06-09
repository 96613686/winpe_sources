# GetTempPathW_0

- ea: `0x180078ba0`
- end: `0x180078ba6`
- name: `GetTempPathW_0`
- size: `6`
- prototype: `DWORD __stdcall(DWORD nBufferLength, LPWSTR lpBuffer)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180078ba0`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall GetTempPathW_0(DWORD nBufferLength, LPWSTR lpBuffer)
{
  return GetTempPathW(nBufferLength, lpBuffer);
}

```

## disassembly

```asm
0x180078ba0  jmp     cs:__imp_GetTempPathW
```
