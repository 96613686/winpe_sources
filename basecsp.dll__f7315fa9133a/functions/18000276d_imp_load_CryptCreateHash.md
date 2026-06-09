# __imp_load_CryptCreateHash

- ea: `0x18000276d`
- end: `0x180002779`
- name: `__imp_load_CryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800025f2`

## import_xrefs

- `CRYPTSP!CryptCreateHash` at `0x18000276d`

## pseudocode

```c
__int64 load_CryptCreateHash()
{
  return _tailMerge_cryptsp_dll();
}

```

## disassembly

```asm
0x18000276d  lea     rax, __imp_CryptCreateHash
0x180002774  jmp     __tailMerge_cryptsp_dll
```
