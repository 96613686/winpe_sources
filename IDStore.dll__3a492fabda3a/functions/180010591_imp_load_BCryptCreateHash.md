# __imp_load_BCryptCreateHash

- ea: `0x180010591`
- end: `0x18001059d`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180010512`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180010591`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x180010591  lea     rax, __imp_BCryptCreateHash
0x180010598  jmp     __tailMerge_bcrypt_dll
```
