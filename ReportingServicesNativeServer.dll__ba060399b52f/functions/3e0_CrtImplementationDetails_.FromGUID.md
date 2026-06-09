# ::<CrtImplementationDetails>.FromGUID

- ea: `0x3e0`
- end: `0x424`
- name: `::<CrtImplementationDetails>.FromGUID`
- size: `68`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x430`
- `0x4e0`

## pseudocode

```c

```

## disassembly

```asm
0x3e0  ldloca.s 0
0x3e2  ldarg.0
0x3e3  ldind.i4
0x3e4  ldarg.0
0x3e5  ldc.i4.4
0x3e6  conv.i8
0x3e7  add
0x3e8  ldind.u2
0x3e9  ldarg.0
0x3ea  ldc.i4.6
0x3eb  conv.i8
0x3ec  add
0x3ed  ldind.u2
0x3ee  ldarg.0
0x3ef  ldc.i4.8
0x3f0  conv.i8
0x3f1  add
0x3f2  ldind.u1
0x3f3  ldarg.0
0x3f4  ldc.i4.s 9
0x3f6  conv.i8
0x3f7  add
0x3f8  ldind.u1
0x3f9  ldarg.0
0x3fa  ldc.i4.s 0xA
0x3fc  conv.i8
0x3fd  add
0x3fe  ldind.u1
0x3ff  ldarg.0
0x400  ldc.i4.s 0xB
0x402  conv.i8
0x403  add
0x404  ldind.u1
0x405  ldarg.0
0x406  ldc.i4.s 0xC
0x408  conv.i8
0x409  add
0x40a  ldind.u1
0x40b  ldarg.0
0x40c  ldc.i4.s 0xD
0x40e  conv.i8
0x40f  add
0x410  ldind.u1
0x411  ldarg.0
0x412  ldc.i4.s 0xE
0x414  conv.i8
0x415  add
0x416  ldind.u1
0x417  ldarg.0
0x418  ldc.i4.s 0xF
0x41a  conv.i8
0x41b  add
0x41c  ldind.u1
0x41d  call     instance void [mscorlib]System.Guid::.ctor(unsigned int32, unsigned int16, unsigned int16, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8)
0x422  ldloc.0
0x423  ret
```
