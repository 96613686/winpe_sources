# _dynamic_initializer_for__gs_registryWatcher__

- ea: `0x180001d30`
- end: `0x180001d3c`
- name: `_dynamic_initializer_for__gs_registryWatcher__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002718`

## pseudocode

```c
int dynamic_initializer_for__gs_registryWatcher__()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__gs_registryWatcher__);
}

```

## disassembly

```asm
0x180001d30  lea     rcx, _dynamic_atexit_destructor_for__gs_registryWatcher__
0x180001d37  jmp     atexit
```
