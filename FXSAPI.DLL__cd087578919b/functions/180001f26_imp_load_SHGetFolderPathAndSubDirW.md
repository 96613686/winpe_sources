# __imp_load_SHGetFolderPathAndSubDirW

- ea: `0x180001f26`
- end: `0x180001f32`
- name: `__imp_load_SHGetFolderPathAndSubDirW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001e5f`

## import_xrefs

- `SHELL32!SHGetFolderPathAndSubDirW` at `0x180001f26`

## pseudocode

```c
__int64 load_SHGetFolderPathAndSubDirW()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x180001f26  lea     rax, __imp_SHGetFolderPathAndSubDirW
0x180001f2d  jmp     __tailMerge_shell32_dll
```
