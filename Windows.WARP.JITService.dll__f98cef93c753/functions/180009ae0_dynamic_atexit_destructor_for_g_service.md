# _dynamic_atexit_destructor_for__g_service__

- ea: `0x180009ae0`
- end: `0x180009aec`
- name: `_dynamic_atexit_destructor_for__g_service__`
- size: `12`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007e80`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_service__()
{
  Service::~Service((Service *)&g_service);
}

```

## disassembly

```asm
0x180009ae0  lea     rcx, ?g_service@@3VService@@A; this
0x180009ae7  jmp     ??1Service@@QEAA@XZ; Service::~Service(void)
```
