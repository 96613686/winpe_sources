# ::<CrtImplementationDetails>.FromGUID

- ea: `0x1f0`
- end: `0x234`
- name: `::<CrtImplementationDetails>.FromGUID`
- size: `68`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x240`
- `0x2f0`

## pseudocode

```c

```

## disassembly

```asm
0x1f0  ldloca.s 0
0x1f2  ldarg.0
0x1f3  ldind.i4
0x1f4  ldarg.0
0x1f5  ldc.i4.4
0x1f6  conv.i8
0x1f7  add
0x1f8  ldind.u2
0x1f9  ldarg.0
0x1fa  ldc.i4.6
0x1fb  conv.i8
0x1fc  add
0x1fd  ldind.u2
0x1fe  ldarg.0
0x1ff  ldc.i4.8
0x200  conv.i8
0x201  add
0x202  ldind.u1
0x203  ldarg.0
0x204  ldc.i4.s 9
0x206  conv.i8
0x207  add
0x208  ldind.u1
0x209  ldarg.0
0x20a  ldc.i4.s 0xA
0x20c  conv.i8
0x20d  add
0x20e  ldind.u1
0x20f  ldarg.0
0x210  ldc.i4.s 0xB
0x212  conv.i8
0x213  add
0x214  ldind.u1
0x215  ldarg.0
0x216  ldc.i4.s 0xC
0x218  conv.i8
0x219  add
0x21a  ldind.u1
0x21b  ldarg.0
0x21c  ldc.i4.s 0xD
0x21e  conv.i8
0x21f  add
0x220  ldind.u1
0x221  ldarg.0
0x222  ldc.i4.s 0xE
0x224  conv.i8
0x225  add
0x226  ldind.u1
0x227  ldarg.0
0x228  ldc.i4.s 0xF
0x22a  conv.i8
0x22b  add
0x22c  ldind.u1
0x22d  call     instance void [mscorlib]System.Guid::.ctor(unsigned int32, unsigned int16, unsigned int16, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8, unsigned int8)
0x232  ldloc.0
0x233  ret
```
