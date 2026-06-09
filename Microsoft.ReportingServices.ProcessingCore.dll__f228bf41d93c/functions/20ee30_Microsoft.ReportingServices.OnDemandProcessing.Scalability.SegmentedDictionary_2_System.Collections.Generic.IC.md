# Microsoft.ReportingServices.OnDemandProcessing.Scalability.SegmentedDictionary`2::System.Collections.Generic.ICollection<System.Collections.Generic.KeyValuePair<TKey,TValue>>.CopyTo

- ea: `0x20ee30`
- end: `0x20eecd`
- name: `Microsoft.ReportingServices.OnDemandProcessing.Scalability.SegmentedDictionary`2::System.Collections.Generic.ICollection<System.Collections.Generic.KeyValuePair<TKey,TValue>>.CopyTo`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x20ee30`

## string_xrefs

- `0x20ee3a`: `SegmentedDictionary.CopyTo: Index must be greater than 0`
- `0x20ee4d`: `SegmentedDictionary.CopyTo: Specified array must not be null`
- `0x20ee66`: `SegmentedDictionary.CopyTo: Specified array must be 1 dimensional`
- `0x20ee91`: `SegmentedDictionary.CopyTo: Insufficent space in destination array`

## pseudocode

```c

```

## disassembly

```asm
0x20ee30  ldarg.2
0x20ee31  ldc.i4.0
0x20ee32  bge.s    loc_20EE44
0x20ee34  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20ee39  ldc.i4.0
0x20ee3a  ldstr    aSegmenteddicti_0// "SegmentedDictionary.CopyTo: Index must "...
0x20ee3f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x20ee44  ldarg.1
0x20ee45  brtrue.s loc_20EE57
0x20ee47  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20ee4c  ldc.i4.0
0x20ee4d  ldstr    aSegmenteddicti_1// "SegmentedDictionary.CopyTo: Specified a"...
0x20ee52  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x20ee57  ldarg.1
0x20ee58  callvirt instance int32 [mscorlib]System.Array::get_Rank()
0x20ee5d  ldc.i4.1
0x20ee5e  ble.s    loc_20EE7E
0x20ee60  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20ee65  ldc.i4.0
0x20ee66  ldstr    aSegmenteddicti_2// "SegmentedDictionary.CopyTo: Specified a"...
0x20ee6b  ldc.i4.1
0x20ee6c  newarr   [mscorlib]System.Object
0x20ee71  dup
0x20ee72  ldc.i4.0
0x20ee73  ldstr    aArray// "array"
0x20ee78  stelem.ref
0x20ee79  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string, object[])
0x20ee7e  ldarg.2
0x20ee7f  ldarg.0
0x20ee80  call     instance int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.SegmentedDictionary`2<var<u1>, !!T0>::get_Count()
0x20ee85  add
0x20ee86  ldarg.1
0x20ee87  ldlen
0x20ee88  conv.i4
0x20ee89  ble.s    loc_20EE9B
0x20ee8b  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20ee90  ldc.i4.0
0x20ee91  ldstr    aSegmenteddicti_3// "SegmentedDictionary.CopyTo: Insufficent"...
0x20ee96  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x20ee9b  ldarg.0
0x20ee9c  call     instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.SegmentedDictionary`2<var<u1>, !!T0>::GetEnumerator()
0x20eea1  stloc.0
0x20eea2  br.s     loc_20EEB8
0x20eea4  ldloc.0
0x20eea5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>>::get_Current()
0x20eeaa  stloc.1
0x20eeab  ldarg.1
0x20eeac  ldarg.2
0x20eead  ldloc.1
0x20eeae  stelem   valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>
0x20eeb3  ldarg.2
0x20eeb4  ldc.i4.1
0x20eeb5  add
0x20eeb6  starg.s  2
0x20eeb8  ldloc.0
0x20eeb9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x20eebe  brtrue.s loc_20EEA4
0x20eec0  leave.s  loc_20EECC
0x20eec2  ldloc.0
0x20eec3  brfalse.s loc_20EECB
0x20eec5  ldloc.0
0x20eec6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20eecb  endfinally
0x20eecc  ret
```
