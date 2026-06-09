# GetCurrentProcessId_0

- ea: `0x180001bd6`
- end: `0x180001bdc`
- name: `GetCurrentProcessId_0`
- size: `6`
- prototype: `DWORD __stdcall()`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x180018a30`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180001bd6`

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
0x180001bd6  jmp     cs:__imp_GetCurrentProcessId
```
