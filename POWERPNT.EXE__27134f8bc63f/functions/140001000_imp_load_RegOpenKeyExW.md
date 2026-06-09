# __imp_load_RegOpenKeyExW

- ea: `0x140001000`
- end: `0x14000100c`
- name: `__imp_load_RegOpenKeyExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1400015d0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140001000`

## pseudocode

```c
__int64 load_RegOpenKeyExW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x140001000  lea     rax, __imp_RegOpenKeyExW
0x140001007  jmp     __tailMerge_advapi32_dll
```
