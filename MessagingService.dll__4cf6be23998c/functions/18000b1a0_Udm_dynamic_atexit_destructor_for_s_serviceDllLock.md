# Udm::_dynamic_atexit_destructor_for__s_serviceDllLock__

- ea: `0x18000b1a0`
- end: `0x18000b1ae`
- name: `Udm::_dynamic_atexit_destructor_for__s_serviceDllLock__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b1a7`

## pseudocode

```c
void Udm::_dynamic_atexit_destructor_for__s_serviceDllLock__()
{
  DeleteCriticalSection(&stru_1800139D0);
}

```

## disassembly

```asm
0x18000b1a0  lea     rcx, stru_1800139D0
0x18000b1a7  jmp     cs:__imp_DeleteCriticalSection
```
