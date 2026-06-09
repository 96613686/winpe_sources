# _dynamic_atexit_destructor_for__g_calendarColorLock__

- ea: `0x18000a650`
- end: `0x18000a65e`
- name: `_dynamic_atexit_destructor_for__g_calendarColorLock__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a657`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_calendarColorLock__()
{
  DeleteCriticalSection(&g_calendarColorLock);
}

```

## disassembly

```asm
0x18000a650  lea     rcx, ?g_calendarColorLock@@3Vrecursive_mutex@utl@@A; utl::recursive_mutex g_calendarColorLock
0x18000a657  jmp     cs:__imp_DeleteCriticalSection
```
