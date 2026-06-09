# __imp_load_SHGetKnownFolderPath

- ea: `0x140002566`
- end: `0x140002572`
- name: `__imp_load_SHGetKnownFolderPath`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140001ab0`

## import_xrefs

- `SHELL32!SHGetKnownFolderPath` at `0x140002566`

## pseudocode

```c
__int64 load_SHGetKnownFolderPath()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x140002566  lea     rax, __imp_SHGetKnownFolderPath
0x14000256d  jmp     __tailMerge_shell32_dll
```
