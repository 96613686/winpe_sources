# __imp_load_FwRegDeleteValue

- ea: `0x180020850`
- end: `0x18002085c`
- name: `__imp_load_FwRegDeleteValue`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!FwRegDeleteValue` at `0x180020850`

## pseudocode

```c
__int64 load_FwRegDeleteValue()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x180020850  lea     rax, __imp_FwRegDeleteValue
0x180020857  jmp     __tailMerge_fwbase_dll
```
