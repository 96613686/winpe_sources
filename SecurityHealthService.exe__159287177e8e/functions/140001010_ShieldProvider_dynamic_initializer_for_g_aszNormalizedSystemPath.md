# ShieldProvider::_dynamic_initializer_for__g_aszNormalizedSystemPath__

- ea: `0x140001010`
- end: `0x14000101c`
- name: `ShieldProvider::_dynamic_initializer_for__g_aszNormalizedSystemPath__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x1400018a0`

## pseudocode

```c
int ShieldProvider::_dynamic_initializer_for__g_aszNormalizedSystemPath__()
{
  return atexit((void (__cdecl *)())ShieldProvider::_dynamic_atexit_destructor_for__g_aszNormalizedSystemPath__);
}

```

## disassembly

```asm
0x140001010  lea     rcx, ShieldProvider___dynamic_atexit_destructor_for__g_aszNormalizedSystemPath__
0x140001017  jmp     atexit
```
