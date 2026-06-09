# __imp_load_SLUninstallProofOfPurchase

- ea: `0x180001d4f`
- end: `0x180001d5b`
- name: `__imp_load_SLUninstallProofOfPurchase`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180001c76`

## import_xrefs

- `sppc!SLUninstallProofOfPurchase` at `0x180001d4f`

## pseudocode

```c
__int64 load_SLUninstallProofOfPurchase()
{
  return _tailMerge_sppc_dll();
}

```

## disassembly

```asm
0x180001d4f  lea     rax, __imp_SLUninstallProofOfPurchase
0x180001d56  jmp     __tailMerge_sppc_dll
```
