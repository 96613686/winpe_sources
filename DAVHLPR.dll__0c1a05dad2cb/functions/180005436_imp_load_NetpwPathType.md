# __imp_load_NetpwPathType

- ea: `0x180005436`
- end: `0x180005442`
- name: `__imp_load_NetpwPathType`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800053a5`

## import_xrefs

- `netutils!NetpwPathType` at `0x180005436`

## pseudocode

```c
__int64 load_NetpwPathType()
{
  return _tailMerge_netutils_dll();
}

```

## disassembly

```asm
0x180005436  lea     rax, __imp_NetpwPathType
0x18000543d  jmp     __tailMerge_netutils_dll
```
