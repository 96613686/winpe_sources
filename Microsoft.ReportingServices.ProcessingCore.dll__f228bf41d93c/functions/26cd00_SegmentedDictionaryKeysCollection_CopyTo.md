# SegmentedDictionaryKeysCollection::CopyTo

- ea: `0x26cd00`
- end: `0x26cd8f`
- name: `SegmentedDictionaryKeysCollection::CopyTo`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x26cd00`

## string_xrefs

- `0x26cd0a`: `SegmentedDictionaryKeysCollection.CopyTo: Index must be greater than 0`
- `0x26cd1d`: `SegmentedDictionaryKeysCollection.CopyTo: Specified array must not be null`
- `0x26cd36`: `SegmentedDictionaryKeysCollection.CopyTo: Specified array must be 1 dimensional`
- `0x26cd53`: `SegmentedDictionaryKeysCollection.CopyTo: Insufficent space in destination array`

## pseudocode

```c

```

## disassembly

```asm
0x26cd00  ldarg.2
0x26cd01  ldc.i4.0
0x26cd02  bge.s    loc_26CD14
0x26cd04  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26cd09  ldc.i4.0
0x26cd0a  ldstr    aSegmenteddicti_8// "SegmentedDictionaryKeysCollection.CopyT"...
0x26cd0f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26cd14  ldarg.1
0x26cd15  brtrue.s loc_26CD27
0x26cd17  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26cd1c  ldc.i4.0
0x26cd1d  ldstr    aSegmenteddicti_9// "SegmentedDictionaryKeysCollection.CopyT"...
0x26cd22  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26cd27  ldarg.1
0x26cd28  callvirt instance int32 [mscorlib]System.Array::get_Rank()
0x26cd2d  ldc.i4.1
0x26cd2e  ble.s    loc_26CD40
0x26cd30  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26cd35  ldc.i4.0
0x26cd36  ldstr    aSegmenteddicti_10// "SegmentedDictionaryKeysCollection.CopyT"...
0x26cd3b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26cd40  ldarg.2
0x26cd41  ldarg.0
0x26cd42  call     instance int32 class SegmentedDictionaryKeysCollection<var<u1>, !!T0>::get_Count()
0x26cd47  add
0x26cd48  ldarg.1
0x26cd49  ldlen
0x26cd4a  conv.i4
0x26cd4b  ble.s    loc_26CD5D
0x26cd4d  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26cd52  ldc.i4.0
0x26cd53  ldstr    aSegmenteddicti_11// "SegmentedDictionaryKeysCollection.CopyT"...
0x26cd58  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26cd5d  ldarg.0
0x26cd5e  call     instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class SegmentedDictionaryKeysCollection<var<u1>, !!T0>::GetEnumerator()
0x26cd63  stloc.0
0x26cd64  br.s     loc_26CD7A
0x26cd66  ldloc.0
0x26cd67  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>>::get_Current()
0x26cd6c  stloc.1
0x26cd6d  ldarg.1
0x26cd6e  ldarg.2
0x26cd6f  ldloc.1
0x26cd70  stelem   var<u1>
0x26cd75  ldarg.2
0x26cd76  ldc.i4.1
0x26cd77  add
0x26cd78  starg.s  2
0x26cd7a  ldloc.0
0x26cd7b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26cd80  brtrue.s loc_26CD66
0x26cd82  leave.s  loc_26CD8E
0x26cd84  ldloc.0
0x26cd85  brfalse.s loc_26CD8D
0x26cd87  ldloc.0
0x26cd88  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26cd8d  endfinally
0x26cd8e  ret
```
