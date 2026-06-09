# _dynamic_atexit_destructor_for__g_critSecLock__

- ea: `0x18000a690`
- end: `0x18000a69e`
- name: `_dynamic_atexit_destructor_for__g_critSecLock__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a697`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_critSecLock__()
{
  DeleteCriticalSection(&g_critSecLock);
}

```

## disassembly

```asm
0x18000a690  lea     rcx, ?g_critSecLock@@3VTridentVersionHelper_StaticLock@@A; TridentVersionHelper_StaticLock g_critSecLock
0x18000a697  jmp     cs:__imp_DeleteCriticalSection
```
