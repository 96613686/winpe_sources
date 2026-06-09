# __imp_load_SHGetFolderPathW

- ea: `0x180003761`
- end: `0x18000376d`
- name: `__imp_load_SHGetFolderPathW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800036e2`

## import_xrefs

- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x180003761`

## pseudocode

```c
__int64 load_SHGetFolderPathW()
{
  return _tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003761  lea     rax, __imp_SHGetFolderPathW
0x180003768  jmp     __tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll
```
