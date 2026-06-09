# __imp_load_SHGetPathFromIDListW

- ea: `0x180002c19`
- end: `0x180002c25`
- name: `__imp_load_SHGetPathFromIDListW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002b40`

## import_xrefs

- `SHELL32!SHGetPathFromIDListW` at `0x180002c19`

## pseudocode

```c
__int64 load_SHGetPathFromIDListW()
{
  return _tailMerge_shell32_dll();
}

```

## disassembly

```asm
0x180002c19  lea     rax, __imp_SHGetPathFromIDListW
0x180002c20  jmp     __tailMerge_shell32_dll
```
