# __imp_load_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z

- ea: `0x1800020b3`
- end: `0x1800020bf`
- name: `__imp_load_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002034`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800020b3`

## pseudocode

```c
__int64 load__IEConfiguration_GetCLSID__YAPEBU_GUID__W4IEConfigurationID___Z()
{
  return _tailMerge_iertutil_dll();
}

```

## disassembly

```asm
0x1800020b3  lea     rax, __imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x1800020ba  jmp     __tailMerge_iertutil_dll
```
