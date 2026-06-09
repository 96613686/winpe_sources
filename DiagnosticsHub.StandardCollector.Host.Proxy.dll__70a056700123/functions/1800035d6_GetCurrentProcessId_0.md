# GetCurrentProcessId_0

- ea: `0x1800035d6`
- end: `0x1800035dc`
- name: `GetCurrentProcessId_0`
- size: `6`
- prototype: `DWORD __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800035d6`

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
0x1800035d6  jmp     cs:__imp_GetCurrentProcessId
```
