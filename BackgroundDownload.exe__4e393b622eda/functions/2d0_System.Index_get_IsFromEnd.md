# System.Index::get_IsFromEnd

- ea: `0x2d0`
- end: `0x2da`
- name: `System.Index::get_IsFromEnd`
- size: `10`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x2e0`
- `0x350`
- `0x4e0`

## pseudocode

```c

```

## disassembly

```asm
0x2d0  ldarg.0
0x2d1  ldfld    int32 System.Index::_value
0x2d6  ldc.i4.0
0x2d7  clt
0x2d9  ret
```
