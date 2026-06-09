# __imp_load_NgcDeleteUserIdKey

- ea: `0x1800047ad`
- end: `0x1800047b9`
- name: `__imp_load_NgcDeleteUserIdKey`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000470a`

## import_xrefs

- `cryptngc!NgcDeleteUserIdKey` at `0x1800047ad`

## pseudocode

```c
__int64 load_NgcDeleteUserIdKey()
{
  return _tailMerge_cryptngc_dll();
}

```

## disassembly

```asm
0x1800047ad  lea     rax, __imp_NgcDeleteUserIdKey
0x1800047b4  jmp     __tailMerge_cryptngc_dll
```
