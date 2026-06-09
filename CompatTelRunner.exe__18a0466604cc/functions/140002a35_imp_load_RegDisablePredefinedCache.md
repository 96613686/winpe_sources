# __imp_load_RegDisablePredefinedCache

- ea: `0x140002a35`
- end: `0x140002a41`
- name: `__imp_load_RegDisablePredefinedCache`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1400029b6`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDisablePredefinedCache` at `0x140002a35`

## pseudocode

```c
__int64 load_RegDisablePredefinedCache()
{
  return _tailMerge_api_ms_win_core_registry_l2_1_0_dll();
}

```

## disassembly

```asm
0x140002a35  lea     rax, __imp_RegDisablePredefinedCache
0x140002a3c  jmp     __tailMerge_api_ms_win_core_registry_l2_1_0_dll
```
