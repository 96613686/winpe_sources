# __imp_load_GetPropMemSize

- ea: `0x18000266c`
- end: `0x180002678`
- name: `__imp_load_GetPropMemSize`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1800025ed`

## import_xrefs

- `UserDataTypeHelperUtil!GetPropMemSize` at `0x18000266c`

## pseudocode

```c
__int64 load_GetPropMemSize()
{
  return _tailMerge_userdatatypehelperutil_dll();
}

```

## disassembly

```asm
0x18000266c  lea     rax, __imp_GetPropMemSize
0x180002673  jmp     __tailMerge_userdatatypehelperutil_dll
```
