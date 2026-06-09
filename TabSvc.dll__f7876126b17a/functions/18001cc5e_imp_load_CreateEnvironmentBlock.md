# __imp_load_CreateEnvironmentBlock

- ea: `0x18001cc5e`
- end: `0x18001cc6a`
- name: `__imp_load_CreateEnvironmentBlock`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001cbcd`

## import_xrefs

- `USERENV!CreateEnvironmentBlock` at `0x18001cc5e`

## pseudocode

```c
__int64 load_CreateEnvironmentBlock()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x18001cc5e  lea     rax, __imp_CreateEnvironmentBlock
0x18001cc65  jmp     __tailMerge_userenv_dll
```
