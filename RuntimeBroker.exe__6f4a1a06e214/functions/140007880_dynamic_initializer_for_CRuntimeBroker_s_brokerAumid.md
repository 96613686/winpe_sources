# _dynamic_initializer_for__CRuntimeBroker::s_brokerAumid__

- ea: `0x140007880`
- end: `0x14000788c`
- name: `_dynamic_initializer_for__CRuntimeBroker::s_brokerAumid__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008f18`

## pseudocode

```c
int dynamic_initializer_for__CRuntimeBroker::s_brokerAumid__()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__CRuntimeBroker::s_brokerAumid__);
}

```

## disassembly

```asm
0x140007880  lea     rcx, _dynamic_atexit_destructor_for__CRuntimeBroker__s_brokerAumid__
0x140007887  jmp     atexit
```
