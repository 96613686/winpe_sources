# _dynamic_initializer_for__g_hUpdatePolicyModule__

- ea: `0x180002190`
- end: `0x18000219c`
- name: `_dynamic_initializer_for__g_hUpdatePolicyModule__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180002b08`

## pseudocode

```c
int dynamic_initializer_for__g_hUpdatePolicyModule__()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_hUpdatePolicyModule__);
}

```

## disassembly

```asm
0x180002190  lea     rcx, _dynamic_atexit_destructor_for__g_hUpdatePolicyModule__
0x180002197  jmp     atexit
```
