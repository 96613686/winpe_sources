# _dynamic_initializer_for__g_PitrDll__

- ea: `0x1800014a0`
- end: `0x1800014ac`
- name: `_dynamic_initializer_for__g_PitrDll__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001cc4`

## pseudocode

```c
int dynamic_initializer_for__g_PitrDll__()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_PitrDll__);
}

```

## disassembly

```asm
0x1800014a0  lea     rcx, _dynamic_atexit_destructor_for__g_PitrDll__
0x1800014a7  jmp     atexit
```
