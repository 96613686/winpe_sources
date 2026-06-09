# __imp_load_SetupDiOpenDevRegKey

- ea: `0x180003c18`
- end: `0x180003c24`
- name: `__imp_load_SetupDiOpenDevRegKey`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180003b75`

## import_xrefs

- `SETUPAPI!SetupDiOpenDevRegKey` at `0x180003c18`

## pseudocode

```c
__int64 load_SetupDiOpenDevRegKey()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x180003c18  lea     rax, __imp_SetupDiOpenDevRegKey
0x180003c1f  jmp     __tailMerge_setupapi_dll
```
