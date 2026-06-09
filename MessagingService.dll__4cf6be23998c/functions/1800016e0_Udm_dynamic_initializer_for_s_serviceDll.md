# Udm::_dynamic_initializer_for__s_serviceDll__

- ea: `0x1800016e0`
- end: `0x1800016ec`
- name: `Udm::_dynamic_initializer_for__s_serviceDll__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002634`

## pseudocode

```c
int Udm::_dynamic_initializer_for__s_serviceDll__()
{
  return atexit((void (__cdecl *)())Udm::_dynamic_atexit_destructor_for__s_serviceDll__);
}

```

## disassembly

```asm
0x1800016e0  lea     rcx, Udm___dynamic_atexit_destructor_for__s_serviceDll__
0x1800016e7  jmp     atexit
```
