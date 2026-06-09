# __imp_load_SHGetPathFromIDListA

- ea: `0x180002bf5`
- end: `0x180002c01`
- name: `__imp_load_SHGetPathFromIDListA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002b40`

## import_xrefs

- `SHELL32!SHGetPathFromIDListA` at `0x180002bf5`

## pseudocode

```c
__int64 load_SHGetPathFromIDListA()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x180002bf5  lea     rax, __imp_SHGetPathFromIDListA
0x180002bfc  jmp     __tailMerge_shell32_dll
```
