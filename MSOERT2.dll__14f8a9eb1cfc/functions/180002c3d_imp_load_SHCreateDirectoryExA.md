# __imp_load_SHCreateDirectoryExA

- ea: `0x180002c3d`
- end: `0x180002c49`
- name: `__imp_load_SHCreateDirectoryExA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002b40`

## import_xrefs

- `SHELL32!SHCreateDirectoryExA` at `0x180002c3d`

## pseudocode

```c
__int64 load_SHCreateDirectoryExA()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x180002c3d  lea     rax, __imp_SHCreateDirectoryExA
0x180002c44  jmp     __tailMerge_shell32_dll
```
