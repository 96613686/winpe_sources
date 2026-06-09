# __imp_load_FWGetConfig

- ea: `0x180002d31`
- end: `0x180002d3d`
- name: `__imp_load_FWGetConfig`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180002c6a`

## import_xrefs

- `FirewallAPI!FWGetConfig` at `0x180002d31`

## pseudocode

```c
__int64 load_FWGetConfig()
{
  return _tailMerge_firewallapi_dll();
}

```

## disassembly

```asm
0x180002d31  lea     rax, __imp_FWGetConfig
0x180002d38  jmp     __tailMerge_firewallapi_dll
```
