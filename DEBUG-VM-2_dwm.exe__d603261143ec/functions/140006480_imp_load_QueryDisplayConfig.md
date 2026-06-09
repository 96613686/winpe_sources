# __imp_load_QueryDisplayConfig

- ea: `0x140006480`
- end: `0x14000648c`
- name: `__imp_load_QueryDisplayConfig`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1400063ef`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!QueryDisplayConfig` at `0x140006480`

## pseudocode

```c
__int64 load_QueryDisplayConfig()
{
  return _tailMerge_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll();
}

```

## disassembly

```asm
0x140006480  lea     rax, __imp_QueryDisplayConfig
0x140006487  jmp     __tailMerge_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll
```
