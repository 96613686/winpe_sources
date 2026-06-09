# GetCurrentProcessId_0

- ea: `0x180016cec`
- end: `0x180016cf2`
- name: `GetCurrentProcessId_0`
- size: `6`
- prototype: `DWORD __stdcall()`
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x180022b14`
- `0x180022c78`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016cec`

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
0x180016cec  jmp     cs:__imp_GetCurrentProcessId
```
