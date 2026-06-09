# _dynamic_initializer_for__g_stringComMgr__

- ea: `0x180001070`
- end: `0x18000107c`
- name: `_dynamic_initializer_for__g_stringComMgr__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001938`

## pseudocode

```c
int dynamic_initializer_for__g_stringComMgr__()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_stringComMgr__);
}

```

## disassembly

```asm
0x180001070  lea     rcx, _dynamic_atexit_destructor_for__g_stringComMgr__
0x180001077  jmp     atexit
```
