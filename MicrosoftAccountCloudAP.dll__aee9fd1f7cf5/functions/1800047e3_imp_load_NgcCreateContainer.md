# __imp_load_NgcCreateContainer

- ea: `0x1800047e3`
- end: `0x1800047ef`
- name: `__imp_load_NgcCreateContainer`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000470a`

## import_xrefs

- `cryptngc!NgcCreateContainer` at `0x1800047e3`

## pseudocode

```c
__int64 load_NgcCreateContainer()
{
  return _tailMerge_cryptngc_dll();
}

```

## disassembly

```asm
0x1800047e3  lea     rax, __imp_NgcCreateContainer
0x1800047ea  jmp     __tailMerge_cryptngc_dll
```
