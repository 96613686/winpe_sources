# __imp_load_CryptCreateHash

- ea: `0x1800159a3`
- end: `0x1800159af`
- name: `__imp_load_CryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800158a6`

## import_xrefs

- `CRYPTSP!CryptCreateHash` at `0x1800159a3`

## pseudocode

```c
__int64 load_CryptCreateHash()
{
  return _tailMerge_cryptsp_dll();
}

```

## disassembly

```asm
0x1800159a3  lea     rax, __imp_CryptCreateHash
0x1800159aa  jmp     __tailMerge_cryptsp_dll
```
