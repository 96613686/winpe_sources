# __imp_load_DeleteAppContainerProfile

- ea: `0x1800088ec`
- end: `0x1800088f8`
- name: `__imp_load_DeleteAppContainerProfile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008849`

## import_xrefs

- `USERENV!DeleteAppContainerProfile` at `0x1800088ec`

## pseudocode

```c
__int64 load_DeleteAppContainerProfile()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x1800088ec  lea     rax, __imp_DeleteAppContainerProfile
0x1800088f3  jmp     __tailMerge_userenv_dll
```
