# System.Index::.ctor

- ea: `0xe0`
- end: `0xfd`
- name: `System.Index::.ctor`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0xe0`
- `0x1110`

## pseudocode

```c

```

## disassembly

```asm
0xe0  ldarg.1
0xe1  ldc.i4.0
0xe2  bge.s    loc_E9
0xe4  call     void ThrowHelper::ThrowValueArgumentOutOfRange_NeedNonNegNumException()
0xe9  ldarg.2
0xea  brfalse.s loc_F5
0xec  ldarg.0
0xed  ldarg.1
0xee  not
0xef  stfld    int32 System.Index::_value
0xf4  ret
0xf5  ldarg.0
0xf6  ldarg.1
0xf7  stfld    int32 System.Index::_value
0xfc  ret
```
