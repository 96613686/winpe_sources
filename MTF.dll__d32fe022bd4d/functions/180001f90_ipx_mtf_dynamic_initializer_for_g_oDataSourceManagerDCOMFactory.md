# ipx::mtf::_dynamic_initializer_for__g_oDataSourceManagerDCOMFactory__

- ea: `0x180001f90`
- end: `0x180001f9c`
- name: `ipx::mtf::_dynamic_initializer_for__g_oDataSourceManagerDCOMFactory__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002864`

## pseudocode

```c
int ipx::mtf::_dynamic_initializer_for__g_oDataSourceManagerDCOMFactory__()
{
  return atexit((void (__cdecl *)())ipx::mtf::_dynamic_atexit_destructor_for__g_oDataSourceManagerDCOMFactory__);
}

```

## disassembly

```asm
0x180001f90  lea     rcx, ipx__mtf___dynamic_atexit_destructor_for__g_oDataSourceManagerDCOMFactory__
0x180001f97  jmp     atexit
```
