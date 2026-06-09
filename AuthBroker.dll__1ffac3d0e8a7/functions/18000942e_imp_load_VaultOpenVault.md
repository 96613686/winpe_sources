# __imp_load_VaultOpenVault

- ea: `0x18000942e`
- end: `0x18000943a`
- name: `__imp_load_VaultOpenVault`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009367`

## import_xrefs

- `VAULTCLI!VaultOpenVault` at `0x18000942e`

## pseudocode

```c
__int64 load_VaultOpenVault()
{
  return _tailMerge_vaultcli_dll();
}

```

## disassembly

```asm
0x18000942e  lea     rax, __imp_VaultOpenVault
0x180009435  jmp     __tailMerge_vaultcli_dll
```
