# __imp_load_FwArrayCreateFromRegistry

- ea: `0x1800208e0`
- end: `0x1800208ec`
- name: `__imp_load_FwArrayCreateFromRegistry`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!FwArrayCreateFromRegistry` at `0x1800208e0`

## pseudocode

```c
__int64 load_FwArrayCreateFromRegistry()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x1800208e0  lea     rax, __imp_FwArrayCreateFromRegistry
0x1800208e7  jmp     __tailMerge_fwbase_dll
```
