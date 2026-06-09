# _dynamic_initializer_for__g_ApxService__

- ea: `0x180001120`
- end: `0x18000112c`
- name: `_dynamic_initializer_for__g_ApxService__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001910`

## pseudocode

```c
int dynamic_initializer_for__g_ApxService__()
{
  return atexit(dynamic_atexit_destructor_for__g_ApxService__);
}

```

## disassembly

```asm
0x180001120  lea     rcx, _dynamic_atexit_destructor_for__g_ApxService__
0x180001127  jmp     atexit
```
