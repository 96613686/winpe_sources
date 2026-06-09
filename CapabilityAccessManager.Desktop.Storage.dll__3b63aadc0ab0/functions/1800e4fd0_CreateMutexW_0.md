# CreateMutexW_0

- ea: `0x1800e4fd0`
- end: `0x1800e4fd6`
- name: `CreateMutexW_0`
- size: `6`
- prototype: `HANDLE __stdcall(LPSECURITY_ATTRIBUTES lpMutexAttributes, BOOL bInitialOwner, LPCWSTR lpName)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800e4fd0`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall CreateMutexW_0(LPSECURITY_ATTRIBUTES lpMutexAttributes, BOOL bInitialOwner, LPCWSTR lpName)
{
  return CreateMutexW(lpMutexAttributes, bInitialOwner, lpName);
}

```

## disassembly

```asm
0x1800e4fd0  jmp     cs:__imp_CreateMutexW
```
