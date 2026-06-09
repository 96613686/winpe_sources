# __imp_load_SetupDiSetClassInstallParamsW

- ea: `0x18000ac56`
- end: `0x18000ac62`
- name: `__imp_load_SetupDiSetClassInstallParamsW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18000ab47`

## import_xrefs

- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x18000ac56`

## pseudocode

```c
__int64 load_SetupDiSetClassInstallParamsW()
{
  return _tailMerge_setupapi_dll();
}

```

## disassembly

```asm
0x18000ac56  lea     rax, __imp_SetupDiSetClassInstallParamsW
0x18000ac5d  jmp     __tailMerge_setupapi_dll
```
