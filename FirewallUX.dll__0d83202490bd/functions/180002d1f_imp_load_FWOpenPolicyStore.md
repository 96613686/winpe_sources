# __imp_load_FWOpenPolicyStore

- ea: `0x180002d1f`
- end: `0x180002d2b`
- name: `__imp_load_FWOpenPolicyStore`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180002c6a`

## import_xrefs

- `FirewallAPI!FWOpenPolicyStore` at `0x180002d1f`

## pseudocode

```c
__int64 load_FWOpenPolicyStore()
{
  return _tailMerge_firewallapi_dll();
}

```

## disassembly

```asm
0x180002d1f  lea     rax, __imp_FWOpenPolicyStore
0x180002d26  jmp     __tailMerge_firewallapi_dll
```
