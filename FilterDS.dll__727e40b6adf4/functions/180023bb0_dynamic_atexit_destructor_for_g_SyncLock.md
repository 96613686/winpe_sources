# _dynamic_atexit_destructor_for__g_SyncLock__

- ea: `0x180023bb0`
- end: `0x180023bbe`
- name: `_dynamic_atexit_destructor_for__g_SyncLock__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023bb7`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_SyncLock__()
{
  DeleteCriticalSection(&g_SyncLock);
}

```

## disassembly

```asm
0x180023bb0  lea     rcx, ?g_SyncLock@@3VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection g_SyncLock
0x180023bb7  jmp     cs:__imp_DeleteCriticalSection
```
