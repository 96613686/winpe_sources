# GetCurrentProcessId_0

- ea: `0x140002980`
- end: `0x140002986`
- name: `GetCurrentProcessId_0`
- size: `6`
- prototype: `DWORD __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002980`

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
0x140002980  jmp     cs:__imp_GetCurrentProcessId
```
