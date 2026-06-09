# _beginthreadex

- ea: `0x1800271fb`
- end: `0x180027201`
- name: `_beginthreadex`
- size: `6`
- prototype: `uintptr_t __cdecl(void *Security, unsigned int StackSize, _beginthreadex_proc_type StartAddress, void *ArgList, unsigned int InitFlag, unsigned int *ThrdAddr)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180010a10`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x1800271fb`

## pseudocode

```c
// attributes: thunk
uintptr_t __cdecl beginthreadex(
        void *Security,
        unsigned int StackSize,
        _beginthreadex_proc_type StartAddress,
        void *ArgList,
        unsigned int InitFlag,
        unsigned int *ThrdAddr)
{
  return _beginthreadex(Security, StackSize, StartAddress, ArgList, InitFlag, ThrdAddr);
}

```

## disassembly

```asm
0x1800271fb  jmp     cs:__imp__beginthreadex
```
