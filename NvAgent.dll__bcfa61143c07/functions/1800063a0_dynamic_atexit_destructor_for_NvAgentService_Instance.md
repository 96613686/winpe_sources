# _dynamic_atexit_destructor_for__NvAgentService::Instance__

- ea: `0x1800063a0`
- end: `0x1800063ac`
- name: `_dynamic_atexit_destructor_for__NvAgentService::Instance__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005ad8`

## pseudocode

```c
void dynamic_atexit_destructor_for__NvAgentService::Instance__()
{
  NvAgentService::~NvAgentService((NvAgentService *)&NvAgentService::Instance);
}

```

## disassembly

```asm
0x1800063a0  lea     rcx, ?Instance@NvAgentService@@2V1@A; this
0x1800063a7  jmp     ??1NvAgentService@@QEAA@XZ; NvAgentService::~NvAgentService(void)
```
