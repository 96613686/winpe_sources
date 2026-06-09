# __imp_load_NgcDeleteContainer

- ea: `0x1800047bf`
- end: `0x1800047cb`
- name: `__imp_load_NgcDeleteContainer`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000470a`

## import_xrefs

- `cryptngc!NgcDeleteContainer` at `0x1800047bf`

## pseudocode

```c
__int64 load_NgcDeleteContainer()
{
  return _tailMerge_cryptngc_dll();
}

```

## disassembly

```asm
0x1800047bf  lea     rax, __imp_NgcDeleteContainer
0x1800047c6  jmp     __tailMerge_cryptngc_dll
```
