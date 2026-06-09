# __imp_load_SetupDiCallClassInstaller

- ea: `0x18000ac68`
- end: `0x18000ac74`
- name: `__imp_load_SetupDiCallClassInstaller`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18000ab47`

## import_xrefs

- `SETUPAPI!SetupDiCallClassInstaller` at `0x18000ac68`

## pseudocode

```c
__int64 load_SetupDiCallClassInstaller()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x18000ac68  lea     rax, __imp_SetupDiCallClassInstaller
0x18000ac6f  jmp     __tailMerge_setupapi_dll
```
