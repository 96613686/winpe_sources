# GetCurrentProcessId_0

- ea: `0x180003d56`
- end: `0x180003d5c`
- name: `GetCurrentProcessId_0`
- size: `6`
- prototype: `DWORD __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180003d56`

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
0x180003d56  jmp     cs:__imp_GetCurrentProcessId
```
