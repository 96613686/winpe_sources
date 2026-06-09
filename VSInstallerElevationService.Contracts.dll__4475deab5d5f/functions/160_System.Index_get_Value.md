# System.Index::get_Value

- ea: `0x160`
- end: `0x178`
- name: `System.Index::get_Value`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x200`
- `0x220`
- `0x390`

## callees

- `0x160`

## pseudocode

```c

```

## disassembly

```asm
0x160  ldarg.0
0x161  ldfld    int32 System.Index::_value
0x166  ldc.i4.0
0x167  bge.s    loc_171
0x169  ldarg.0
0x16a  ldfld    int32 System.Index::_value
0x16f  not
0x170  ret
0x171  ldarg.0
0x172  ldfld    int32 System.Index::_value
0x177  ret
```
