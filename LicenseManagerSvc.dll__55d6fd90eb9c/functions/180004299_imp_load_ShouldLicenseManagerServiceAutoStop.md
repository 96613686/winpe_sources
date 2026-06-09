# __imp_load_ShouldLicenseManagerServiceAutoStop

- ea: `0x180004299`
- end: `0x1800042a5`
- name: `__imp_load_ShouldLicenseManagerServiceAutoStop`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000421a`

## import_xrefs

- `ext-ms-win-core-licensemanager-l1-1-0!ShouldLicenseManagerServiceAutoStop` at `0x180004299`

## pseudocode

```c
__int64 load_ShouldLicenseManagerServiceAutoStop()
{
  return _tailMerge_ext_ms_win_core_licensemanager_l1_1_0_dll();
}

```

## disassembly

```asm
0x180004299  lea     rax, __imp_ShouldLicenseManagerServiceAutoStop
0x1800042a0  jmp     __tailMerge_ext_ms_win_core_licensemanager_l1_1_0_dll
```
