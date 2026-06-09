# _dynamic_atexit_destructor_for__IncomingTextMessageHandler::sm_instanceLock__

- ea: `0x18000b150`
- end: `0x18000b15e`
- name: `_dynamic_atexit_destructor_for__IncomingTextMessageHandler::sm_instanceLock__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b157`

## pseudocode

```c
void dynamic_atexit_destructor_for__IncomingTextMessageHandler::sm_instanceLock__()
{
  DeleteCriticalSection(&IncomingTextMessageHandler::sm_instanceLock);
}

```

## disassembly

```asm
0x18000b150  lea     rcx, ?sm_instanceLock@IncomingTextMessageHandler@@0Vrecursive_mutex@utl@@A; utl::recursive_mutex IncomingTextMessageHandler::sm_instanceLock
0x18000b157  jmp     cs:__imp_DeleteCriticalSection
```
