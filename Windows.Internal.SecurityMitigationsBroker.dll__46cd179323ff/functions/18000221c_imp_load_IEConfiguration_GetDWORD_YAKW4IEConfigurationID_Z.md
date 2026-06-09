# __imp_load_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z

- ea: `0x18000221c`
- end: `0x180002228`
- name: `__imp_load_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180002034`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18000221c`

## pseudocode

```c
__int64 load__IEConfiguration_GetDWORD__YAKW4IEConfigurationID___Z()
{
  return _tailMerge_iertutil_dll();
}

```

## disassembly

```asm
0x18000221c  lea     rax, __imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180002223  jmp     __tailMerge_iertutil_dll
```
