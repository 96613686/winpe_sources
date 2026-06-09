# __imp_load_SHCreateDirectoryExW

- ea: `0x180003877`
- end: `0x180003883`
- name: `__imp_load_SHCreateDirectoryExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800037f8`

## import_xrefs

- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x180003877`

## pseudocode

```c
__int64 load_SHCreateDirectoryExW()
{
  return _tailMerge_api_ms_win_shell_shdirectory_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003877  lea     rax, __imp_SHCreateDirectoryExW
0x18000387e  jmp     __tailMerge_api_ms_win_shell_shdirectory_l1_1_0_dll
```
