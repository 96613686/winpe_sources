# __imp_load_BCryptCreateHash

- ea: `0x18002762a`
- end: `0x180027636`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800275a5`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18002762a`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x18002762a  lea     rax, __imp_BCryptCreateHash
0x180027631  jmp     __tailMerge_bcrypt_dll
```
