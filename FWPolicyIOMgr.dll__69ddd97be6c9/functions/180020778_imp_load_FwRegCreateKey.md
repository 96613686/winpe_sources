# __imp_load_FwRegCreateKey

- ea: `0x180020778`
- end: `0x180020784`
- name: `__imp_load_FwRegCreateKey`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!FwRegCreateKey` at `0x180020778`

## pseudocode

```c
__int64 load_FwRegCreateKey()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x180020778  lea     rax, __imp_FwRegCreateKey
0x18002077f  jmp     __tailMerge_fwbase_dll
```
