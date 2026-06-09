# ::<CrtImplementationDetails>.DefaultDomain.HasPerProcess

- ea: `0x580`
- end: `0x5c7`
- name: `::<CrtImplementationDetails>.DefaultDomain.HasPerProcess`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x650`

## callees

- `0x580`

## pseudocode

```c

```

## disassembly

```asm
0x580  ldsfld   valuetype <CrtImplementationDetails>.TriBool ?hasPerProcess@DefaultDomain@<CrtImplementationDetails>@@0W4TriBool@2@A
0x585  ldc.i4.2
0x586  bne.un.s loc_5BD
0x588  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.$ArrayType$$$BY00Q6MPEBXXZ __xc_mp_a
0x58d  stloc.0
0x58e  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.$ArrayType$$$BY00Q6MPEBXXZ __xc_mp_a
0x593  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.$ArrayType$$$BY00Q6MPEBXXZ __xc_mp_z
0x598  bge.un.s loc_5B5
0x59a  ldloc.0
0x59b  ldind.i8
0x59c  brtrue.s loc_5AD
0x59e  ldloc.0
0x59f  ldc.i4.8
0x5a0  conv.i8
0x5a1  add
0x5a2  stloc.0
0x5a3  ldloc.0
0x5a4  ldsflda  modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype <CppImplementationDetails>.$ArrayType$$$BY00Q6MPEBXXZ __xc_mp_z
0x5a9  blt.un.s loc_59A
0x5ab  br.s     loc_5B5
0x5ad  ldc.i4.m1
0x5ae  stsfld   valuetype <CrtImplementationDetails>.TriBool ?hasPerProcess@DefaultDomain@<CrtImplementationDetails>@@0W4TriBool@2@A
0x5b3  ldc.i4.1
0x5b4  ret
0x5b5  ldc.i4.0
0x5b6  stsfld   valuetype <CrtImplementationDetails>.TriBool ?hasPerProcess@DefaultDomain@<CrtImplementationDetails>@@0W4TriBool@2@A
0x5bb  ldc.i4.0
0x5bc  ret
0x5bd  ldsfld   valuetype <CrtImplementationDetails>.TriBool ?hasPerProcess@DefaultDomain@<CrtImplementationDetails>@@0W4TriBool@2@A
0x5c2  ldc.i4.m1
0x5c3  ceq
0x5c5  conv.u1
0x5c6  ret
```
