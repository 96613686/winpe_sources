# __imp_load_RegOpenKeyExW

- ea: `0x18002593c`
- end: `0x180025948`
- name: `__imp_load_RegOpenKeyExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800258aa`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18002593c`

## pseudocode

```c
__int64 load_RegOpenKeyExW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18002593c  lea     rax, __imp_RegOpenKeyExW
0x180025943  jmp     __tailMerge_advapi32_dll
```
