# ::_initterm_m

- ea: `0xe10`
- end: `0xe31`
- name: `::_initterm_m`
- size: `33`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x520`
- `0x600`
- `0x640`

## callees

- `0xe10`
- `0xe40`

## pseudocode

```c

```

## disassembly

```asm
0xe10  ldarg.0
0xe11  ldarg.1
0xe12  bge.un.s loc_E30
0xe14  ldarg.0
0xe15  ldind.i8
0xe16  stloc.0
0xe17  ldloc.0
0xe18  brfalse.s loc_E26
0xe1a  ldloc.0
0xe1b  call     modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(()) '<CrtImplementationDetails>.ThisModule.ResolveMethod<void const * __clrcall(void)>'(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(()))
0xe20  calli    T0x11000088
0xe25  pop
0xe26  ldarg.0
0xe27  ldc.i4.8
0xe28  conv.i8
0xe29  add
0xe2a  starg.s  0
0xe2c  ldarg.0
0xe2d  ldarg.1
0xe2e  blt.un.s loc_E14
0xe30  ret
```
