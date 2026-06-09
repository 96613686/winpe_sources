# GetCurrentProcessId_0

- ea: `0x140002fc8`
- end: `0x140002fce`
- name: `GetCurrentProcessId_0`
- size: `6`
- prototype: `DWORD __stdcall()`
- caller_count: `5`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x140016b30`
- `0x140016d80`
- `0x140016ee0`
- `0x140017034`
- `0x1400170a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002fc8`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall GetCurrentProcessId_0()
{
  return GetCurrentProcessId();
}

```

## disassembly

```asm
0x140002fc8  jmp     cs:__imp_GetCurrentProcessId
```
