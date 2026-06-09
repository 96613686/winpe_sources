# _dynamic_initializer_for__g_service__

- ea: `0x180001210`
- end: `0x18000121c`
- name: `_dynamic_initializer_for__g_service__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008e30`

## pseudocode

```c
int dynamic_initializer_for__g_service__()
{
  return atexit(dynamic_atexit_destructor_for__g_service__);
}

```

## disassembly

```asm
0x180001210  lea     rcx, _dynamic_atexit_destructor_for__g_service__
0x180001217  jmp     atexit
```
