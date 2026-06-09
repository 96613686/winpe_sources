# __imp_load_RegSetValueExW

- ea: `0x140001723`
- end: `0x14000172f`
- name: `__imp_load_RegSetValueExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x140001691`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140001723`

## pseudocode

```c
__int64 load_RegSetValueExW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x140001723  lea     rax, __imp_RegSetValueExW
0x14000172a  jmp     __tailMerge_advapi32_dll
```
