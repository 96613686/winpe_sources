# Udm::_dynamic_initializer_for__s_serviceDllLock__

- ea: `0x180001700`
- end: `0x180001726`
- name: `Udm::_dynamic_initializer_for__s_serviceDllLock__`
- size: `38`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002634`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180001710`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180001710`

## pseudocode

```c
int Udm::_dynamic_initializer_for__s_serviceDllLock__()
{
  InitializeCriticalSectionEx(&stru_1800139D0, 0, 0);
  return atexit(Udm::_dynamic_atexit_destructor_for__s_serviceDllLock__);
}

```

## disassembly

```asm
0x180001700  sub     rsp, 28h
0x180001704  xor     r8d, r8d; Flags
0x180001707  lea     rcx, stru_1800139D0; lpCriticalSection
0x18000170e  xor     edx, edx; dwSpinCount
0x180001710  call    cs:__imp_InitializeCriticalSectionEx
0x180001716  lea     rcx, Udm___dynamic_atexit_destructor_for__s_serviceDllLock__
0x18000171d  add     rsp, 28h
0x180001721  jmp     atexit
```
