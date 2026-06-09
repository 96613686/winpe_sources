# __imp_load_BCryptCreateHash

- ea: `0x180001b18`
- end: `0x180001b24`
- name: `__imp_load_BCryptCreateHash`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001990`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180001b18`

## pseudocode

```c
__int64 load_BCryptCreateHash()
{
  return _tailMerge_bcrypt_dll();
}

```

## disassembly

```asm
0x180001b18  lea     rax, __imp_BCryptCreateHash
0x180001b1f  jmp     __tailMerge_bcrypt_dll
```
