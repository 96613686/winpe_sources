# __imp_load_DiUninstallDevice

- ea: `0x180002822`
- end: `0x18000282e`
- name: `__imp_load_DiUninstallDevice`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x1800027a3`

## import_xrefs

- `ext-ms-win-newdev-config-l1-1-0!DiUninstallDevice` at `0x180002822`

## pseudocode

```c
__int64 load_DiUninstallDevice()
{
  return _tailMerge_ext_ms_win_newdev_config_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002822  lea     rax, __imp_DiUninstallDevice
0x180002829  jmp     __tailMerge_ext_ms_win_newdev_config_l1_1_0_dll
```
