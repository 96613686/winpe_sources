# ::_initterm_e

- ea: `0x10a0`
- end: `0x10c2`
- name: `::_initterm_e`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x760`

## callees

- `0x10a0`

## pseudocode

```c

```

## disassembly

```asm
0x10a0  ldc.i4.0
0x10a1  stloc.0
0x10a2  ldarg.0
0x10a3  ldarg.1
0x10a4  bge.un.s loc_10C0
0x10a6  ldloc.0
0x10a7  brtrue.s loc_10C0
0x10a9  ldarg.0
0x10aa  ldind.i8
0x10ab  stloc.1
0x10ac  ldloc.1
0x10ad  brfalse.s loc_10B6
0x10af  ldloc.1
0x10b0  calli    T0x11000050
0x10b5  stloc.0
0x10b6  ldarg.0
0x10b7  ldc.i4.8
0x10b8  conv.i8
0x10b9  add
0x10ba  starg.s  0
0x10bc  ldarg.0
0x10bd  ldarg.1
0x10be  blt.un.s loc_10A6
0x10c0  ldloc.0
0x10c1  ret
```
