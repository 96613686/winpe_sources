# ::<CrtImplementationDetails>.DefaultDomain.HasNative

- ea: `0x5d0`
- end: `0x644`
- name: `::<CrtImplementationDetails>.DefaultDomain.HasNative`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x650`

## callees

- `0x5d0`

## pseudocode

```c

```

## disassembly

```asm
0x5d0  ldsfld   valuetype <CrtImplementationDetails>.TriBool ?hasNative@DefaultDomain@<CrtImplementationDetails>@@0W4TriBool@2@A
0x5d5  ldc.i4.2
0x5d6  bne.un.s loc_63A
0x5d8  ldsflda  valuetype <CppImplementationDetails>.$ArrayType$$$BY0A@P6AHXZ __xi_a
0x5dd  stloc.1
0x5de  ldsflda  valuetype <CppImplementationDetails>.$ArrayType$$$BY0A@P6AHXZ __xi_a
0x5e3  ldsflda  valuetype <CppImplementationDetails>.$ArrayType$$$BY0A@P6AHXZ __xi_z
0x5e8  bge.un.s loc_605
0x5ea  ldloc.1
0x5eb  ldind.i8
0x5ec  brtrue.s loc_5FD
0x5ee  ldloc.1
0x5ef  ldc.i4.8
0x5f0  conv.i8
0x5f1  add
0x5f2  stloc.1
0x5f3  ldloc.1
0x5f4  ldsflda  valuetype <CppImplementationDetails>.$ArrayType$$$BY0A@P6AHXZ __xi_z
0x5f9  blt.un.s loc_5EA
0x5fb  br.s     loc_605
0x5fd  ldc.i4.m1
0x5fe  stsfld   valuetype <CrtImplementationDetails>.TriBool ?hasNative@DefaultDomain@<CrtImplementationDetails>@@0W4TriBool@2@A
0x603  ldc.i4.1
0x604  ret
0x605  ldsflda  valuetype <CppImplementationDetails>.$ArrayType$$$BY0A@P6AXXZ __xc_a
0x60a  stloc.0
0x60b  ldsflda  valuetype <CppImplementationDetails>.$ArrayType$$$BY0A@P6AXXZ __xc_a
0x610  ldsflda  valuetype <CppImplementationDetails>.$ArrayType$$$BY0A@P6AXXZ __xc_z
0x615  bge.un.s loc_632
0x617  ldloc.0
0x618  ldind.i8
0x619  brtrue.s loc_62A
0x61b  ldloc.0
0x61c  ldc.i4.8
0x61d  conv.i8
0x61e  add
0x61f  stloc.0
0x620  ldloc.0
0x621  ldsflda  valuetype <CppImplementationDetails>.$ArrayType$$$BY0A@P6AXXZ __xc_z
0x626  blt.un.s loc_617
0x628  br.s     loc_632
0x62a  ldc.i4.m1
0x62b  stsfld   valuetype <CrtImplementationDetails>.TriBool ?hasNative@DefaultDomain@<CrtImplementationDetails>@@0W4TriBool@2@A
0x630  ldc.i4.1
0x631  ret
0x632  ldc.i4.0
0x633  stsfld   valuetype <CrtImplementationDetails>.TriBool ?hasNative@DefaultDomain@<CrtImplementationDetails>@@0W4TriBool@2@A
0x638  ldc.i4.0
0x639  ret
0x63a  ldsfld   valuetype <CrtImplementationDetails>.TriBool ?hasNative@DefaultDomain@<CrtImplementationDetails>@@0W4TriBool@2@A
0x63f  ldc.i4.m1
0x640  ceq
0x642  conv.u1
0x643  ret
```
