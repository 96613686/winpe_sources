# __imp_load_FWGetGlobalConfig

- ea: `0x180002cfb`
- end: `0x180002d07`
- name: `__imp_load_FWGetGlobalConfig`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180002c6a`

## import_xrefs

- `FirewallAPI!FWGetGlobalConfig` at `0x180002cfb`

## pseudocode

```c
__int64 load_FWGetGlobalConfig()
{
  return _tailMerge_firewallapi_dll();
}

```

## disassembly

```asm
0x180002cfb  lea     rax, __imp_FWGetGlobalConfig
0x180002d02  jmp     __tailMerge_firewallapi_dll
```
