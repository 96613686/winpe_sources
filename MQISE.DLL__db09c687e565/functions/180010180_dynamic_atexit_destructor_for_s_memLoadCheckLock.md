# _dynamic_atexit_destructor_for__s_memLoadCheckLock__

- ea: `0x180010180`
- end: `0x180010197`
- name: `_dynamic_atexit_destructor_for__s_memLoadCheckLock__`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001018b`
- `KERNEL32!DeleteCriticalSection` at `0x18001018b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void dynamic_atexit_destructor_for__s_memLoadCheckLock__()
{
  DeleteCriticalSection(&s_memLoadCheckLock);
}

```

## disassembly

```asm
0x180010180  sub     rsp, 28h
0x180010184  lea     rcx, ?s_memLoadCheckLock@@3VCCriticalSection@@A; lpCriticalSection
0x18001018b  call    cs:__imp_DeleteCriticalSection
0x180010191  nop
0x180010192  add     rsp, 28h
0x180010196  retn
```
