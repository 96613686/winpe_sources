# <PrivateImplementationDetails>::ComputeStringHash

- ea: `0x3e60`
- end: `0x3e8c`
- name: `<PrivateImplementationDetails>::ComputeStringHash`
- size: `44`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xe10`
- `0x1950`
- `0x34f0`

## callees

- `0x3e60`

## pseudocode

```c

```

## disassembly

```asm
0x3e60  ldarg.0
0x3e61  brfalse.s loc_3E8A
0x3e63  ldc.i4   0x811C9DC5
0x3e68  stloc.0
0x3e69  ldc.i4.0
0x3e6a  stloc.1
0x3e6b  br.s     loc_3E81
0x3e6d  ldarg.0
0x3e6e  ldloc.1
0x3e6f  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3e74  ldloc.0
0x3e75  xor
0x3e76  ldc.i4   0x1000193
0x3e7b  mul
0x3e7c  stloc.0
0x3e7d  ldloc.1
0x3e7e  ldc.i4.1
0x3e7f  add
0x3e80  stloc.1
0x3e81  ldloc.1
0x3e82  ldarg.0
0x3e83  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3e88  blt.s    loc_3E6D
0x3e8a  ldloc.0
0x3e8b  ret
```
