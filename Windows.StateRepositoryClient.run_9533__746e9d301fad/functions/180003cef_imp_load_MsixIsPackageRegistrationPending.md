# __imp_load_MsixIsPackageRegistrationPending

- ea: `0x180003cef`
- end: `0x180003cfb`
- name: `__imp_load_MsixIsPackageRegistrationPending`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180003c70`

## import_xrefs

- `ext-ms-onecore-appmodel-deployment-internal-l1-1-1!MsixIsPackageRegistrationPending` at `0x180003cef`

## pseudocode

```c
__int64 load_MsixIsPackageRegistrationPending()
{
  return _tailMerge_ext_ms_onecore_appmodel_deployment_internal_l1_1_1_dll();
}

```

## disassembly

```asm
0x180003cef  lea     rax, __imp_MsixIsPackageRegistrationPending
0x180003cf6  jmp     __tailMerge_ext_ms_onecore_appmodel_deployment_internal_l1_1_1_dll
```
