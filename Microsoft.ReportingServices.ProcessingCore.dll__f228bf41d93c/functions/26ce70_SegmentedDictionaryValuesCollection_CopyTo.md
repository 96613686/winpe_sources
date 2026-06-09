# SegmentedDictionaryValuesCollection::CopyTo

- ea: `0x26ce70`
- end: `0x26ceff`
- name: `SegmentedDictionaryValuesCollection::CopyTo`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x26ce70`

## string_xrefs

- `0x26ce7a`: `SegmentedDictionaryValuesCollection.CopyTo: Index must be greater than 0`
- `0x26ce8d`: `SegmentedDictionaryValuesCollection.CopyTo: Specified array must not be null`
- `0x26cea6`: `SegmentedDictionaryValuesCollection.CopyTo: Specified array must be 1 dimensional`
- `0x26cec3`: `SegmentedDictionaryValuesCollection.CopyTo: Insufficent space in destination array`

## pseudocode

```c

```

## disassembly

```asm
0x26ce70  ldarg.2
0x26ce71  ldc.i4.0
0x26ce72  bge.s    loc_26CE84
0x26ce74  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26ce79  ldc.i4.0
0x26ce7a  ldstr    aSegmenteddicti_15// "SegmentedDictionaryValuesCollection.Cop"...
0x26ce7f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26ce84  ldarg.1
0x26ce85  brtrue.s loc_26CE97
0x26ce87  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26ce8c  ldc.i4.0
0x26ce8d  ldstr    aSegmenteddicti_16// "SegmentedDictionaryValuesCollection.Cop"...
0x26ce92  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26ce97  ldarg.1
0x26ce98  callvirt instance int32 [mscorlib]System.Array::get_Rank()
0x26ce9d  ldc.i4.1
0x26ce9e  ble.s    loc_26CEB0
0x26cea0  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26cea5  ldc.i4.0
0x26cea6  ldstr    aSegmenteddicti_17// "SegmentedDictionaryValuesCollection.Cop"...
0x26ceab  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26ceb0  ldarg.2
0x26ceb1  ldarg.0
0x26ceb2  call     instance int32 class SegmentedDictionaryValuesCollection<var<u1>, !!T0>::get_Count()
0x26ceb7  add
0x26ceb8  ldarg.1
0x26ceb9  ldlen
0x26ceba  conv.i4
0x26cebb  ble.s    loc_26CECD
0x26cebd  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26cec2  ldc.i4.0
0x26cec3  ldstr    aSegmenteddicti_18// "SegmentedDictionaryValuesCollection.Cop"...
0x26cec8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26cecd  ldarg.0
0x26cece  call     instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class SegmentedDictionaryValuesCollection<var<u1>, !!T0>::GetEnumerator()
0x26ced3  stloc.0
0x26ced4  br.s     loc_26CEEA
0x26ced6  ldloc.0
0x26ced7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>>::get_Current()
0x26cedc  stloc.1
0x26cedd  ldarg.1
0x26cede  ldarg.2
0x26cedf  ldloc.1
0x26cee0  stelem   var<u1>
0x26cee5  ldarg.2
0x26cee6  ldc.i4.1
0x26cee7  add
0x26cee8  starg.s  2
0x26ceea  ldloc.0
0x26ceeb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26cef0  brtrue.s loc_26CED6
0x26cef2  leave.s  loc_26CEFE
0x26cef4  ldloc.0
0x26cef5  brfalse.s loc_26CEFD
0x26cef7  ldloc.0
0x26cef8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26cefd  endfinally
0x26cefe  ret
```
