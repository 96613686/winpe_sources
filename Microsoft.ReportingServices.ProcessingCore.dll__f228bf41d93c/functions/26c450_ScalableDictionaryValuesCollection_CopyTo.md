# ScalableDictionaryValuesCollection::CopyTo

- ea: `0x26c450`
- end: `0x26c4df`
- name: `ScalableDictionaryValuesCollection::CopyTo`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x26c450`

## string_xrefs

- `0x26c45a`: `ScalableDictionaryValuesCollection.CopyTo: Index must be greater than 0`
- `0x26c46d`: `ScalableDictionaryValuesCollection.CopyTo: Specified array must not be null`
- `0x26c486`: `ScalableDictionaryValuesCollection.CopyTo: Specified array must be 1 dimensional`
- `0x26c4a3`: `ScalableDictionaryValuesCollection.CopyTo: Insufficent space in destination array`

## pseudocode

```c

```

## disassembly

```asm
0x26c450  ldarg.2
0x26c451  ldc.i4.0
0x26c452  bge.s    loc_26C464
0x26c454  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26c459  ldc.i4.0
0x26c45a  ldstr    aScalabledictio_15// "ScalableDictionaryValuesCollection.Copy"...
0x26c45f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26c464  ldarg.1
0x26c465  brtrue.s loc_26C477
0x26c467  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26c46c  ldc.i4.0
0x26c46d  ldstr    aScalabledictio_16// "ScalableDictionaryValuesCollection.Copy"...
0x26c472  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26c477  ldarg.1
0x26c478  callvirt instance int32 [mscorlib]System.Array::get_Rank()
0x26c47d  ldc.i4.1
0x26c47e  ble.s    loc_26C490
0x26c480  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26c485  ldc.i4.0
0x26c486  ldstr    aScalabledictio_17// "ScalableDictionaryValuesCollection.Copy"...
0x26c48b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26c490  ldarg.2
0x26c491  ldarg.0
0x26c492  call     instance int32 class ScalableDictionaryValuesCollection<var<u1>, !!T0>::get_Count()
0x26c497  add
0x26c498  ldarg.1
0x26c499  ldlen
0x26c49a  conv.i4
0x26c49b  ble.s    loc_26C4AD
0x26c49d  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26c4a2  ldc.i4.0
0x26c4a3  ldstr    aScalabledictio_18// "ScalableDictionaryValuesCollection.Copy"...
0x26c4a8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26c4ad  ldarg.0
0x26c4ae  call     instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class ScalableDictionaryValuesCollection<var<u1>, !!T0>::GetEnumerator()
0x26c4b3  stloc.0
0x26c4b4  br.s     loc_26C4CA
0x26c4b6  ldloc.0
0x26c4b7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>>::get_Current()
0x26c4bc  stloc.1
0x26c4bd  ldarg.1
0x26c4be  ldarg.2
0x26c4bf  ldloc.1
0x26c4c0  stelem   var<u1>
0x26c4c5  ldarg.2
0x26c4c6  ldc.i4.1
0x26c4c7  add
0x26c4c8  starg.s  2
0x26c4ca  ldloc.0
0x26c4cb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26c4d0  brtrue.s loc_26C4B6
0x26c4d2  leave.s  loc_26C4DE
0x26c4d4  ldloc.0
0x26c4d5  brfalse.s loc_26C4DD
0x26c4d7  ldloc.0
0x26c4d8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26c4dd  endfinally
0x26c4de  ret
```
