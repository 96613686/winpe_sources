# __imp_load_SHGetKnownFolderPath

- ea: `0x180008cf5`
- end: `0x180008d01`
- name: `__imp_load_SHGetKnownFolderPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008c76`

## import_xrefs

- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180008cf5`

## pseudocode

```c
__int64 load_SHGetKnownFolderPath()
{
  return _tailMerge_api_ms_win_shell_shellfolders_l1_1_0_dll();
}

```

## disassembly

```asm
0x180008cf5  lea     rax, __imp_SHGetKnownFolderPath
0x180008cfc  jmp     __tailMerge_api_ms_win_shell_shellfolders_l1_1_0_dll
```
