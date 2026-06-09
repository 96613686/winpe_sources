# _dynamic_atexit_destructor_for__g_inprocServiceInitLock__

- ea: `0x1800216a0`
- end: `0x1800216ae`
- name: `_dynamic_atexit_destructor_for__g_inprocServiceInitLock__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800216a7`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_inprocServiceInitLock__()
{
  DeleteCriticalSection(&g_inprocServiceInitLock);
}

```

## disassembly

```asm
0x1800216a0  lea     rcx, ?g_inprocServiceInitLock@@3Vrecursive_mutex@utl@@A; utl::recursive_mutex g_inprocServiceInitLock
0x1800216a7  jmp     cs:__imp_DeleteCriticalSection
```
