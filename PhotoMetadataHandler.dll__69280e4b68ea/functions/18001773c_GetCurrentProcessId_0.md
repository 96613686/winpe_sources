# GetCurrentProcessId_0

- ea: `0x18001773c`
- end: `0x180017742`
- name: `GetCurrentProcessId_0`
- size: `6`
- prototype: `DWORD __stdcall()`
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x180023c44`
- `0x180023db0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001773c`

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
0x18001773c  jmp     cs:__imp_GetCurrentProcessId
```
