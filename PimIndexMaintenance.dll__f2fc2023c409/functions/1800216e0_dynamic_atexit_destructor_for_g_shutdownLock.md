# _dynamic_atexit_destructor_for__g_shutdownLock__

- ea: `0x1800216e0`
- end: `0x1800216ee`
- name: `_dynamic_atexit_destructor_for__g_shutdownLock__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800216e7`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_shutdownLock__()
{
  DeleteCriticalSection(&g_shutdownLock);
}

```

## disassembly

```asm
0x1800216e0  lea     rcx, ?g_shutdownLock@@3Vrecursive_mutex@utl@@A; utl::recursive_mutex g_shutdownLock
0x1800216e7  jmp     cs:__imp_DeleteCriticalSection
```
