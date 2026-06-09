# __imp_load_?InternalSetAccessibilityColorMatrix@@YAJAEAY144M@Z

- ea: `0x1400028f9`
- end: `0x140002905`
- name: `__imp_load_?InternalSetAccessibilityColorMatrix@@YAJAEAY144M@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x14000287a`

## import_xrefs

- `mscms!__imp_?InternalSetAccessibilityColorMatrix@@YAJAEAY144M@Z` at `0x1400028f9`

## pseudocode

```c
__int64 load__InternalSetAccessibilityColorMatrix__YAJAEAY144M_Z()
{
  return _tailMerge_mscms_dll();
}

```

## disassembly

```asm
0x1400028f9  lea     rax, __imp_?InternalSetAccessibilityColorMatrix@@YAJAEAY144M@Z; InternalSetAccessibilityColorMatrix(float (&)[5][5])
0x140002900  jmp     __tailMerge_mscms_dll
```
