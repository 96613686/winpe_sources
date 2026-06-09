# _dynamic_initializer_for__JobExecution::copyManager__

- ea: `0x140001a00`
- end: `0x140001a0c`
- name: `_dynamic_initializer_for__JobExecution::copyManager__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001f94`

## pseudocode

```c
int dynamic_initializer_for__JobExecution::copyManager__()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__JobExecution::copyManager__);
}

```

## disassembly

```asm
0x140001a00  lea     rcx, _dynamic_atexit_destructor_for__JobExecution__copyManager__
0x140001a07  jmp     atexit
```
