# __imp_load_DeleteProfileW

- ea: `0x18000443c`
- end: `0x180004448`
- name: `__imp_load_DeleteProfileW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800043bd`

## import_xrefs

- `USERENV!DeleteProfileW` at `0x18000443c`

## pseudocode

```c
__int64 load_DeleteProfileW()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x18000443c  lea     rax, __imp_DeleteProfileW
0x180004443  jmp     __tailMerge_userenv_dll
```
