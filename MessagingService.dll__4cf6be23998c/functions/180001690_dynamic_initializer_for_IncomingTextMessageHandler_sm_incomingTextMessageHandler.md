# _dynamic_initializer_for__IncomingTextMessageHandler::sm_incomingTextMessageHandler__

- ea: `0x180001690`
- end: `0x18000169c`
- name: `_dynamic_initializer_for__IncomingTextMessageHandler::sm_incomingTextMessageHandler__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002634`

## pseudocode

```c
int dynamic_initializer_for__IncomingTextMessageHandler::sm_incomingTextMessageHandler__()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__IncomingTextMessageHandler::sm_incomingTextMessageHandler__);
}

```

## disassembly

```asm
0x180001690  lea     rcx, _dynamic_atexit_destructor_for__IncomingTextMessageHandler__sm_incomingTextMessageHandler__
0x180001697  jmp     atexit
```
