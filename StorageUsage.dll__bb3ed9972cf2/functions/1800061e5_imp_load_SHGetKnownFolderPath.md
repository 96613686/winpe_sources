# __imp_load_SHGetKnownFolderPath

- ea: `0x1800061e5`
- end: `0x1800061f1`
- name: `__imp_load_SHGetKnownFolderPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006166`

## import_xrefs

- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800061e5`

## pseudocode

```c
__int64 load_SHGetKnownFolderPath()
{
  return _tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800061e5  lea     rax, __imp_SHGetKnownFolderPath
0x1800061ec  jmp     __tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll
```
