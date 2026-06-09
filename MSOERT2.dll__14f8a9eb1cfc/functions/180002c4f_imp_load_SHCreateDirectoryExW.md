# __imp_load_SHCreateDirectoryExW

- ea: `0x180002c4f`
- end: `0x180002c5b`
- name: `__imp_load_SHCreateDirectoryExW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002b40`

## import_xrefs

- `SHELL32!SHCreateDirectoryExW` at `0x180002c4f`

## pseudocode

```c
__int64 load_SHCreateDirectoryExW()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x180002c4f  lea     rax, __imp_SHCreateDirectoryExW
0x180002c56  jmp     __tailMerge_shell32_dll
```
