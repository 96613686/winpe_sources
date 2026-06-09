# __imp_load_ConfigurationManager_Create

- ea: `0x180002e9a`
- end: `0x180002ea6`
- name: `__imp_load_ConfigurationManager_Create`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180002e1b`

## import_xrefs

- `MapConfiguration!ConfigurationManager_Create` at `0x180002e9a`

## pseudocode

```c
__int64 load_ConfigurationManager_Create()
{
  return _tailMerge_mapconfiguration_dll();
}

```

## disassembly

```asm
0x180002e9a  lea     rax, __imp_ConfigurationManager_Create
0x180002ea1  jmp     __tailMerge_mapconfiguration_dll
```
