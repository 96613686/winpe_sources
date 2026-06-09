# GetTempPathA_0

- ea: `0x1800038e0`
- end: `0x1800038e6`
- name: `GetTempPathA_0`
- size: `6`
- prototype: `DWORD __stdcall(DWORD nBufferLength, LPSTR lpBuffer)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-file-l1-2-2!GetTempPathA` at `0x1800038e0`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall GetTempPathA_0(DWORD nBufferLength, LPSTR lpBuffer)
{
  return GetTempPathA(nBufferLength, lpBuffer);
}

```

## disassembly

```asm
0x1800038e0  jmp     cs:__imp_GetTempPathA
```
