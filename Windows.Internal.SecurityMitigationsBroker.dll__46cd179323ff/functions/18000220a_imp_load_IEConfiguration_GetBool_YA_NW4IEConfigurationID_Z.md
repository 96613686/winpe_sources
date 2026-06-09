# __imp_load_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z

- ea: `0x18000220a`
- end: `0x180002216`
- name: `__imp_load_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180002034`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18000220a`

## pseudocode

```c
__int64 load__IEConfiguration_GetBool__YA_NW4IEConfigurationID___Z()
{
  return _tailMerge_iertutil_dll();
}

```

## disassembly

```asm
0x18000220a  lea     rax, __imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180002211  jmp     __tailMerge_iertutil_dll
```
