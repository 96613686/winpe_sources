# ScalableDictionaryKeysCollection::CopyTo

- ea: `0x26c2e0`
- end: `0x26c36f`
- name: `ScalableDictionaryKeysCollection::CopyTo`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x26c2e0`

## string_xrefs

- `0x26c2ea`: `ScalableDictionaryKeysCollection.CopyTo: Index must be greater than 0`
- `0x26c2fd`: `ScalableDictionaryKeysCollection.CopyTo: Specified array must not be null`
- `0x26c316`: `ScalableDictionaryKeysCollection.CopyTo: Specified array must be 1 dimensional`
- `0x26c333`: `ScalableDictionaryKeysCollection.CopyTo: Insufficent space in destination array`

## pseudocode

```c

```

## disassembly

```asm
0x26c2e0  ldarg.2
0x26c2e1  ldc.i4.0
0x26c2e2  bge.s    loc_26C2F4
0x26c2e4  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26c2e9  ldc.i4.0
0x26c2ea  ldstr    aScalabledictio_8// "ScalableDictionaryKeysCollection.CopyTo"...
0x26c2ef  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26c2f4  ldarg.1
0x26c2f5  brtrue.s loc_26C307
0x26c2f7  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26c2fc  ldc.i4.0
0x26c2fd  ldstr    aScalabledictio_9// "ScalableDictionaryKeysCollection.CopyTo"...
0x26c302  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26c307  ldarg.1
0x26c308  callvirt instance int32 [mscorlib]System.Array::get_Rank()
0x26c30d  ldc.i4.1
0x26c30e  ble.s    loc_26C320
0x26c310  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26c315  ldc.i4.0
0x26c316  ldstr    aScalabledictio_10// "ScalableDictionaryKeysCollection.CopyTo"...
0x26c31b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26c320  ldarg.2
0x26c321  ldarg.0
0x26c322  call     instance int32 class ScalableDictionaryKeysCollection<var<u1>, !!T0>::get_Count()
0x26c327  add
0x26c328  ldarg.1
0x26c329  ldlen
0x26c32a  conv.i4
0x26c32b  ble.s    loc_26C33D
0x26c32d  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x26c332  ldc.i4.0
0x26c333  ldstr    aScalabledictio_11// "ScalableDictionaryKeysCollection.CopyTo"...
0x26c338  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x26c33d  ldarg.0
0x26c33e  call     instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class ScalableDictionaryKeysCollection<var<u1>, !!T0>::GetEnumerator()
0x26c343  stloc.0
0x26c344  br.s     loc_26C35A
0x26c346  ldloc.0
0x26c347  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>>::get_Current()
0x26c34c  stloc.1
0x26c34d  ldarg.1
0x26c34e  ldarg.2
0x26c34f  ldloc.1
0x26c350  stelem   var<u1>
0x26c355  ldarg.2
0x26c356  ldc.i4.1
0x26c357  add
0x26c358  starg.s  2
0x26c35a  ldloc.0
0x26c35b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26c360  brtrue.s loc_26C346
0x26c362  leave.s  loc_26C36E
0x26c364  ldloc.0
0x26c365  brfalse.s loc_26C36D
0x26c367  ldloc.0
0x26c368  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26c36d  endfinally
0x26c36e  ret
```
