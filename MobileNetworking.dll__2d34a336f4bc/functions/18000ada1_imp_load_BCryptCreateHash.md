# __imp_load_BCryptCreateHash

- ea: `0x18000ada1`
- end: `0x18000adad`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000acb6`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18000ada1`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x18000ada1  lea     rax, __imp_BCryptCreateHash
0x18000ada8  jmp     __tailMerge_bcrypt_dll
```
