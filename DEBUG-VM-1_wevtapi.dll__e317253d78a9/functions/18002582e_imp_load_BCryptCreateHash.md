# __imp_load_BCryptCreateHash

- ea: `0x18002582e`
- end: `0x18002583a`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180025767`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18002582e`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x18002582e  lea     rax, __imp_BCryptCreateHash
0x180025835  jmp     __tailMerge_bcrypt_dll
```
