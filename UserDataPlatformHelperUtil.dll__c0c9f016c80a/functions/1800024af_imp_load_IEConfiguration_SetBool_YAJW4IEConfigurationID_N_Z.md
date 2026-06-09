# __imp_load_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z

- ea: `0x1800024af`
- end: `0x1800024bb`
- name: `__imp_load_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180002430`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x1800024af`

## pseudocode

```c
__int64 load__IEConfiguration_SetBool__YAJW4IEConfigurationID___N_Z()
{
  return _tailMerge_iertutil_dll();
}

```

## disassembly

```asm
0x1800024af  lea     rax, __imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x1800024b6  jmp     __tailMerge_iertutil_dll
```
