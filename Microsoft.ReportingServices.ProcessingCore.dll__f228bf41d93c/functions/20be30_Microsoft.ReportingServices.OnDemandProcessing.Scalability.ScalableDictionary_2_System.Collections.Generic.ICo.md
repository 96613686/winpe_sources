# Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionary`2::System.Collections.Generic.ICollection<System.Collections.Generic.KeyValuePair<TKey,TValue>>.CopyTo

- ea: `0x20be30`
- end: `0x20becd`
- name: `Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionary`2::System.Collections.Generic.ICollection<System.Collections.Generic.KeyValuePair<TKey,TValue>>.CopyTo`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x20be30`

## string_xrefs

- `0x20be3a`: `ScalableDictionary.CopyTo: Index must be greater than 0`
- `0x20be4d`: `ScalableDictionary.CopyTo: Specified array must not be null`
- `0x20be66`: `ScalableDictionary.CopyTo: Specified array must be 1 dimensional`
- `0x20be91`: `ScalableDictionary.CopyTo: Insufficent space in destination array`

## pseudocode

```c

```

## disassembly

```asm
0x20be30  ldarg.2
0x20be31  ldc.i4.0
0x20be32  bge.s    loc_20BE44
0x20be34  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20be39  ldc.i4.0
0x20be3a  ldstr    aScalabledictio_0// "ScalableDictionary.CopyTo: Index must b"...
0x20be3f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x20be44  ldarg.1
0x20be45  brtrue.s loc_20BE57
0x20be47  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20be4c  ldc.i4.0
0x20be4d  ldstr    aScalabledictio_1// "ScalableDictionary.CopyTo: Specified ar"...
0x20be52  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x20be57  ldarg.1
0x20be58  callvirt instance int32 [mscorlib]System.Array::get_Rank()
0x20be5d  ldc.i4.1
0x20be5e  ble.s    loc_20BE7E
0x20be60  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20be65  ldc.i4.0
0x20be66  ldstr    aScalabledictio_2// "ScalableDictionary.CopyTo: Specified ar"...
0x20be6b  ldc.i4.1
0x20be6c  newarr   [mscorlib]System.Object
0x20be71  dup
0x20be72  ldc.i4.0
0x20be73  ldstr    aArray// "array"
0x20be78  stelem.ref
0x20be79  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string, object[])
0x20be7e  ldarg.2
0x20be7f  ldarg.0
0x20be80  call     instance int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionary`2<var<u1>, !!T0>::get_Count()
0x20be85  add
0x20be86  ldarg.1
0x20be87  ldlen
0x20be88  conv.i4
0x20be89  ble.s    loc_20BE9B
0x20be8b  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20be90  ldc.i4.0
0x20be91  ldstr    aScalabledictio_3// "ScalableDictionary.CopyTo: Insufficent "...
0x20be96  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x20be9b  ldarg.0
0x20be9c  call     instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableDictionary`2<var<u1>, !!T0>::GetEnumerator()
0x20bea1  stloc.0
0x20bea2  br.s     loc_20BEB8
0x20bea4  ldloc.0
0x20bea5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>>::get_Current()
0x20beaa  stloc.1
0x20beab  ldarg.1
0x20beac  ldarg.2
0x20bead  ldloc.1
0x20beae  stelem   valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>
0x20beb3  ldarg.2
0x20beb4  ldc.i4.1
0x20beb5  add
0x20beb6  starg.s  2
0x20beb8  ldloc.0
0x20beb9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x20bebe  brtrue.s loc_20BEA4
0x20bec0  leave.s  loc_20BECC
0x20bec2  ldloc.0
0x20bec3  brfalse.s loc_20BECB
0x20bec5  ldloc.0
0x20bec6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20becb  endfinally
0x20becc  ret
```
