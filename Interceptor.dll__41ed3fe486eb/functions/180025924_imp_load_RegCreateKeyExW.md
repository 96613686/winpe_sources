# __imp_load_RegCreateKeyExW

- ea: `0x180025924`
- end: `0x180025930`
- name: `__imp_load_RegCreateKeyExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800258aa`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x180025924`

## pseudocode

```c
__int64 load_RegCreateKeyExW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180025924  lea     rax, __imp_RegCreateKeyExW
0x18002592b  jmp     __tailMerge_advapi32_dll
```
