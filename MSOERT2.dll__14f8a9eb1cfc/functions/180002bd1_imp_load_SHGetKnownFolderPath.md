# __imp_load_SHGetKnownFolderPath

- ea: `0x180002bd1`
- end: `0x180002bdd`
- name: `__imp_load_SHGetKnownFolderPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002b40`

## import_xrefs

- `SHELL32!SHGetKnownFolderPath` at `0x180002bd1`

## pseudocode

```c
__int64 load_SHGetKnownFolderPath()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x180002bd1  lea     rax, __imp_SHGetKnownFolderPath
0x180002bd8  jmp     __tailMerge_shell32_dll
```
