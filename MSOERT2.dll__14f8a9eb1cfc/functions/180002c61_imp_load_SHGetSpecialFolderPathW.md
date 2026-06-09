# __imp_load_SHGetSpecialFolderPathW

- ea: `0x180002c61`
- end: `0x180002c6d`
- name: `__imp_load_SHGetSpecialFolderPathW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002b40`

## import_xrefs

- `SHELL32!SHGetSpecialFolderPathW` at `0x180002c61`

## pseudocode

```c
__int64 load_SHGetSpecialFolderPathW()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x180002c61  lea     rax, __imp_SHGetSpecialFolderPathW
0x180002c68  jmp     __tailMerge_shell32_dll
```
