# __imp_load_SHGetSpecialFolderPathW

- ea: `0x180003889`
- end: `0x180003895`
- name: `__imp_load_SHGetSpecialFolderPathW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800036e2`

## import_xrefs

- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x180003889`

## pseudocode

```c
__int64 load_SHGetSpecialFolderPathW()
{
  return _tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003889  lea     rax, __imp_SHGetSpecialFolderPathW
0x180003890  jmp     __tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll
```
