# <PrivateImplementationDetails>::ComputeStringHash

- ea: `0x2d10`
- end: `0x2d3c`
- name: `<PrivateImplementationDetails>::ComputeStringHash`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x370`

## callees

- `0x2d10`

## pseudocode

```c

```

## disassembly

```asm
0x2d10  ldarg.0
0x2d11  brfalse.s loc_2D3A
0x2d13  ldc.i4   0x811C9DC5
0x2d18  stloc.0
0x2d19  ldc.i4.0
0x2d1a  stloc.1
0x2d1b  br.s     loc_2D31
0x2d1d  ldarg.0
0x2d1e  ldloc.1
0x2d1f  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2d24  ldloc.0
0x2d25  xor
0x2d26  ldc.i4   0x1000193
0x2d2b  mul
0x2d2c  stloc.0
0x2d2d  ldloc.1
0x2d2e  ldc.i4.1
0x2d2f  add
0x2d30  stloc.1
0x2d31  ldloc.1
0x2d32  ldarg.0
0x2d33  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2d38  blt.s    loc_2D1D
0x2d3a  ldloc.0
0x2d3b  ret
```
