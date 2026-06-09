# __imp_load_RegOpenKeyExW

- ea: `0x1800021dc`
- end: `0x1800021e8`
- name: `__imp_load_RegOpenKeyExW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180001fff`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800021dc`

## pseudocode

```c
__int64 load_RegOpenKeyExW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800021dc  lea     rax, __imp_RegOpenKeyExW
0x1800021e3  jmp     __tailMerge_advapi32_dll
```
