# System.IO.Packaging.Package::ValidateStreamingAccess

- ea: `0x49570`
- end: `0x495e9`
- name: `System.IO.Packaging.Package::ValidateStreamingAccess`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x49320`
- `0x493b0`

## callees

- `0x2c100`
- `0x49570`

## string_xrefs

- `0x4957f`: `StreamingPackageProductionImpliesWriteOnlyAccess`
- `0x495c8`: `StreamingPackageProductionRequiresSingleWriter`

## pseudocode

```c

```

## disassembly

```asm
0x49570  ldarg.3
0x49571  brfalse.s loc_495E8
0x49573  ldarg.0
0x49574  ldc.i4.2
0x49575  beq.s    loc_4957B
0x49577  ldarg.0
0x49578  ldc.i4.1
0x49579  bne.un.s loc_495D8
0x4957b  ldarg.1
0x4957c  ldc.i4.2
0x4957d  beq.s    loc_4958F
0x4957f  ldstr    aStreamingpacka// "StreamingPackageProductionImpliesWriteO"...
0x49584  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x49589  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x4958e  throw
0x4958f  ldarga.s 2
0x49591  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.IO.FileShare>::get_HasValue()
0x49596  brfalse.s loc_495E8
0x49598  ldarg.2
0x49599  stloc.0
0x4959a  ldc.i4.1
0x4959b  stloc.1
0x4959c  ldloca.s 0
0x4959e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.IO.FileShare>::GetValueOrDefault()
0x495a3  ldloc.1
0x495a4  ceq
0x495a6  ldloca.s 0
0x495a8  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.IO.FileShare>::get_HasValue()
0x495ad  and
0x495ae  brtrue.s loc_495E8
0x495b0  ldarg.2
0x495b1  stloc.0
0x495b2  ldc.i4.0
0x495b3  stloc.1
0x495b4  ldloca.s 0
0x495b6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.IO.FileShare>::GetValueOrDefault()
0x495bb  ldloc.1
0x495bc  ceq
0x495be  ldloca.s 0
0x495c0  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.IO.FileShare>::get_HasValue()
0x495c5  and
0x495c6  brtrue.s loc_495E8
0x495c8  ldstr    aStreamingpacka_0// "StreamingPackageProductionRequiresSingl"...
0x495cd  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x495d2  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x495d7  throw
0x495d8  ldstr    aStreamingmoden// "StreamingModeNotSupportedForConsumption"
0x495dd  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x495e2  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x495e7  throw
0x495e8  ret
```
