# <PrivateImplementationDetails>::ComputeStringHash

- ea: `0x1440`
- end: `0x146c`
- name: `<PrivateImplementationDetails>::ComputeStringHash`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xe0`
- `0xd30`

## callees

- `0x1440`

## pseudocode

```c

```

## disassembly

```asm
0x1440  ldc.i4   0x811C9DC5
0x1445  stloc.0
0x1446  ldarg.0
0x1447  brfalse.s loc_146A
0x1449  ldc.i4.0
0x144a  stloc.1
0x144b  br.s     loc_1461
0x144d  ldarg.0
0x144e  ldloc.1
0x144f  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x1454  ldloc.0
0x1455  xor
0x1456  ldc.i4   0x1000193
0x145b  mul
0x145c  stloc.0
0x145d  ldloc.1
0x145e  ldc.i4.1
0x145f  add
0x1460  stloc.1
0x1461  ldloc.1
0x1462  ldarg.0
0x1463  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1468  blt.s    loc_144D
0x146a  ldloc.0
0x146b  ret
```
