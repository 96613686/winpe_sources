# __imp_load_GetDisplayConfigBufferSizes

- ea: `0x14000646e`
- end: `0x14000647a`
- name: `__imp_load_GetDisplayConfigBufferSizes`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1400063ef`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetDisplayConfigBufferSizes` at `0x14000646e`

## pseudocode

```c
__int64 load_GetDisplayConfigBufferSizes()
{
  return _tailMerge_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll();
}

```

## disassembly

```asm
0x14000646e  lea     rax, __imp_GetDisplayConfigBufferSizes
0x140006475  jmp     __tailMerge_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll
```
