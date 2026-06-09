# _dynamic_atexit_destructor_for__g_oLock__

- ea: `0x40eb80`
- end: `0x40eb95`
- name: `_dynamic_atexit_destructor_for__g_oLock__`
- size: `21`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x40eb80`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x40eb8e`
- `KERNEL32!DeleteCriticalSection` at `0x40eb8e`

## pseudocode

```c
void __cdecl dynamic_atexit_destructor_for__g_oLock__()
{
  if ( g_oLock )
    DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x40eb80  cmp     ?g_oLock@@3VCLock@@A, 0; CLock g_oLock
0x40eb87  jz      short locret_40EB94
0x40eb89  push    offset CriticalSection; lpCriticalSection
0x40eb8e  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x40eb94  retn
```
