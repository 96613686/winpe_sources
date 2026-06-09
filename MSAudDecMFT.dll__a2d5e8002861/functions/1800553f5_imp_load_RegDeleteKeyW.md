# __imp_load_RegDeleteKeyW

- ea: `0x1800553f5`
- end: `0x180055401`
- name: `__imp_load_RegDeleteKeyW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180055376`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800553f5`

## pseudocode

```c
__int64 load_RegDeleteKeyW()
{
  return _tailMerge_api_ms_win_core_registry_l2_1_0_dll();
}

```

## disassembly

```asm
0x1800553f5  lea     rax, __imp_RegDeleteKeyW
0x1800553fc  jmp     __tailMerge_api_ms_win_core_registry_l2_1_0_dll
```
