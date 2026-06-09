# __imp_load_NgcCreateUserIdKeyEx

- ea: `0x180004807`
- end: `0x180004813`
- name: `__imp_load_NgcCreateUserIdKeyEx`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000470a`

## import_xrefs

- `cryptngc!NgcCreateUserIdKeyEx` at `0x180004807`

## pseudocode

```c
__int64 load_NgcCreateUserIdKeyEx()
{
  return _tailMerge_cryptngc_dll();
}

```

## disassembly

```asm
0x180004807  lea     rax, __imp_NgcCreateUserIdKeyEx
0x18000480e  jmp     __tailMerge_cryptngc_dll
```
