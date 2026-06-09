# ::<CrtImplementationDetails>.DefaultDomain.NeedsInitialization

- ea: `0x650`
- end: `0x67c`
- name: `::<CrtImplementationDetails>.DefaultDomain.NeedsInitialization`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x880`

## callees

- `0x580`
- `0x5d0`
- `0x650`

## pseudocode

```c

```

## disassembly

```asm
0x650  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) bool <CrtImplementationDetails>.DefaultDomain.HasPerProcess()
0x655  brfalse.s loc_65E
0x657  ldsfld   bool ?InitializedPerProcess@DefaultDomain@<CrtImplementationDetails>@@2_NA
0x65c  brfalse.s loc_673
0x65e  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) bool <CrtImplementationDetails>.DefaultDomain.HasNative()
0x663  brfalse.s loc_677
0x665  ldsfld   bool ?InitializedNative@DefaultDomain@<CrtImplementationDetails>@@2_NA
0x66a  brtrue.s loc_677
0x66c  ldsfld   valuetype __scrt_native_startup_state __scrt_current_native_startup_state
0x671  brtrue.s loc_677
0x673  ldc.i4.1
0x674  stloc.0
0x675  br.s     loc_679
0x677  ldc.i4.0
0x678  stloc.0
0x679  ldloc.0
0x67a  conv.u1
0x67b  ret
```
