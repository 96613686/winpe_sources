# __imp_load_BCryptCreateHash

- ea: `0x1800023eb`
- end: `0x1800023f7`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002300`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x1800023eb`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x1800023eb  lea     rax, __imp_BCryptCreateHash
0x1800023f2  jmp     __tailMerge_bcrypt_dll
```
