# System.Index::Equals

- ea: `0x1b0`
- end: `0x1ce`
- name: `System.Index::Equals`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1b0`

## pseudocode

```c

```

## disassembly

```asm
0x1b0  ldarg.1
0x1b1  isinst   System.Index
0x1b6  brfalse.s loc_1CC
0x1b8  ldarg.0
0x1b9  ldfld    int32 System.Index::_value
0x1be  ldarg.1
0x1bf  unbox    System.Index
0x1c4  ldfld    int32 System.Index::_value
0x1c9  ceq
0x1cb  ret
0x1cc  ldc.i4.0
0x1cd  ret
```
