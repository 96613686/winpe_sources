# __imp_load_NgcDeleteContainerEx

- ea: `0x1800047d1`
- end: `0x1800047dd`
- name: `__imp_load_NgcDeleteContainerEx`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000470a`

## import_xrefs

- `cryptngc!NgcDeleteContainerEx` at `0x1800047d1`

## pseudocode

```c
__int64 load_NgcDeleteContainerEx()
{
  return _tailMerge_cryptngc_dll();
}

```

## disassembly

```asm
0x1800047d1  lea     rax, __imp_NgcDeleteContainerEx
0x1800047d8  jmp     __tailMerge_cryptngc_dll
```
