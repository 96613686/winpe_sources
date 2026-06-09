# _dynamic_atexit_destructor_for__TaskLock__

- ea: `0x14001f000`
- end: `0x14001f00e`
- name: `_dynamic_atexit_destructor_for__TaskLock__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14001f007`

## pseudocode

```c
void dynamic_atexit_destructor_for__TaskLock__()
{
  DeleteCriticalSection(&TaskLock);
}

```

## disassembly

```asm
0x14001f000  lea     rcx, ?TaskLock@@3UAUTOINIT_CRITICAL_SECTION@@A; AUTOINIT_CRITICAL_SECTION TaskLock
0x14001f007  jmp     cs:__imp_DeleteCriticalSection
```
