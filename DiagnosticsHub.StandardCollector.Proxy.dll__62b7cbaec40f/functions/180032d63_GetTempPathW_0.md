# GetTempPathW_0

- ea: `0x180032d63`
- end: `0x180032d69`
- name: `GetTempPathW_0`
- size: `6`
- prototype: `DWORD __stdcall(DWORD nBufferLength, LPWSTR lpBuffer)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!GetTempPathW` at `0x180032d63`

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
0x180032d63  jmp     cs:__imp_GetTempPathW
```
