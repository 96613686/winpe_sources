# System.Index::get_Value

- ea: `0x2b0`
- end: `0x2c8`
- name: `System.Index::get_Value`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x350`
- `0x370`
- `0x4e0`

## callees

- `0x2b0`

## pseudocode

```c

```

## disassembly

```asm
0x2b0  ldarg.0
0x2b1  ldfld    int32 System.Index::_value
0x2b6  ldc.i4.0
0x2b7  bge.s    loc_2C1
0x2b9  ldarg.0
0x2ba  ldfld    int32 System.Index::_value
0x2bf  not
0x2c0  ret
0x2c1  ldarg.0
0x2c2  ldfld    int32 System.Index::_value
0x2c7  ret
```
