# _dynamic_initializer_for__NvAgentService::Instance__

- ea: `0x180001120`
- end: `0x18000112c`
- name: `_dynamic_initializer_for__NvAgentService::Instance__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001940`

## pseudocode

```c
int dynamic_initializer_for__NvAgentService::Instance__()
{
  return atexit(dynamic_atexit_destructor_for__NvAgentService::Instance__);
}

```

## disassembly

```asm
0x180001120  lea     rcx, _dynamic_atexit_destructor_for__NvAgentService__Instance__
0x180001127  jmp     atexit
```
