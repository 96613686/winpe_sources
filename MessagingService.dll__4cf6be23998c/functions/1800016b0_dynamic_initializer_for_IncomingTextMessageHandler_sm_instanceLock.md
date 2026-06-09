# _dynamic_initializer_for__IncomingTextMessageHandler::sm_instanceLock__

- ea: `0x1800016b0`
- end: `0x1800016d6`
- name: `_dynamic_initializer_for__IncomingTextMessageHandler::sm_instanceLock__`
- size: `38`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002634`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800016c0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800016c0`

## pseudocode

```c
int dynamic_initializer_for__IncomingTextMessageHandler::sm_instanceLock__()
{
  InitializeCriticalSectionEx(&IncomingTextMessageHandler::sm_instanceLock, 0, 0);
  return atexit(dynamic_atexit_destructor_for__IncomingTextMessageHandler::sm_instanceLock__);
}

```

## disassembly

```asm
0x1800016b0  sub     rsp, 28h
0x1800016b4  xor     r8d, r8d; Flags
0x1800016b7  lea     rcx, ?sm_instanceLock@IncomingTextMessageHandler@@0Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800016be  xor     edx, edx; dwSpinCount
0x1800016c0  call    cs:__imp_InitializeCriticalSectionEx
0x1800016c6  lea     rcx, _dynamic_atexit_destructor_for__IncomingTextMessageHandler__sm_instanceLock__
0x1800016cd  add     rsp, 28h
0x1800016d1  jmp     atexit
```
