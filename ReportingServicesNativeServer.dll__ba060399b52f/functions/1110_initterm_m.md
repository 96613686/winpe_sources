# ::_initterm_m

- ea: `0x1110`
- end: `0x1131`
- name: `::_initterm_m`
- size: `33`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x710`
- `0x7f0`
- `0x830`

## callees

- `0x1110`
- `0x1140`

## pseudocode

```c

```

## disassembly

```asm
0x1110  ldarg.0
0x1111  ldarg.1
0x1112  bge.un.s loc_1130
0x1114  ldarg.0
0x1115  ldind.i8
0x1116  stloc.0
0x1117  ldloc.0
0x1118  brfalse.s loc_1126
0x111a  ldloc.0
0x111b  call     modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(()) '<CrtImplementationDetails>.ThisModule.ResolveMethod<void const * __clrcall(void)>'(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) void*(()))
0x1120  calli    T0x11000051
0x1125  pop
0x1126  ldarg.0
0x1127  ldc.i4.8
0x1128  conv.i8
0x1129  add
0x112a  starg.s  0
0x112c  ldarg.0
0x112d  ldarg.1
0x112e  blt.un.s loc_1114
0x1130  ret
```
