# __imp_load_SHGetKnownFolderPath

- ea: `0x1800022ac`
- end: `0x1800022b8`
- name: `__imp_load_SHGetKnownFolderPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000222d`

## import_xrefs

- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800022ac`

## pseudocode

```c
__int64 load_SHGetKnownFolderPath()
{
  return _tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800022ac  lea     rax, __imp_SHGetKnownFolderPath
0x1800022b3  jmp     __tailMerge_ext_ms_win_shell32_shellfolders_l1_1_0_dll
```
