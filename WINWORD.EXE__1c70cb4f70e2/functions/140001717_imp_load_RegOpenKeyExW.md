# __imp_load_RegOpenKeyExW

- ea: `0x140001717`
- end: `0x140001723`
- name: `__imp_load_RegOpenKeyExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x140001691`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140001717`

## pseudocode

```c
__int64 load_RegOpenKeyExW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x140001717  lea     rax, __imp_RegOpenKeyExW
0x14000171e  jmp     __tailMerge_advapi32_dll
```
