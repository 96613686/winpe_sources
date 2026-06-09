# Microsoft.ReportingServices.ReportIntermediateFormat.GroupTreeTracer::TraceDataSetInstance

- ea: `0x144140`
- end: `0x144223`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.GroupTreeTracer::TraceDataSetInstance`
- size: `227`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x143ca0`
- `0x143dc0`

## callees

- `0xd8700`
- `0xd8720`
- `0xd8740`
- `0xd8770`
- `0xd87b0`
- `0xd87d0`
- `0xd87f0`
- `0xd8810`
- `0xd8830`
- `0x114be0`
- `0x143d80`
- `0x143f50`
- `0x144140`

## string_xrefs

- `0x144158`: `{0}DataSet={1}, NoRows={2}, RowCount={3}, Lcid={4}, CS={5}, AS={6}, KS={7}, WS={8}, CommandText={9}`

## pseudocode

```c

```

## disassembly

```asm
0x144140  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x144145  ldarg.0
0x144146  ldnull
0x144147  cgt.un
0x144149  ldstr    aNullInstance// "(null != instance)"
0x14414e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x144153  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x144158  ldstr    a0Dataset1Norow// "{0}DataSet={1}, NoRows={2}, RowCount={3"...
0x14415d  ldc.i4.s 0xA
0x14415f  newarr   [mscorlib]System.Object
0x144164  dup
0x144165  ldc.i4.0
0x144166  ldarg.1
0x144167  call     string Microsoft.ReportingServices.ReportIntermediateFormat.GroupTreeTracer::GetEmptyString(int32 level)
0x14416c  stelem.ref
0x14416d  dup
0x14416e  ldc.i4.1
0x14416f  ldarg.0
0x144170  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance::get_DataSetDef()
0x144175  brtrue.s loc_14417A
0x144177  ldnull
0x144178  br.s     loc_144185
0x14417a  ldarg.0
0x14417b  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.DataSet Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance::get_DataSetDef()
0x144180  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSet::get_Name()
0x144185  stelem.ref
0x144186  dup
0x144187  ldc.i4.2
0x144188  ldarg.0
0x144189  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance::get_NoRows()
0x14418e  box      [mscorlib]System.Boolean
0x144193  stelem.ref
0x144194  dup
0x144195  ldc.i4.3
0x144196  ldarg.0
0x144197  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance::get_RecordSetSize()
0x14419c  box      [mscorlib]System.Int32
0x1441a1  stelem.ref
0x1441a2  dup
0x1441a3  ldc.i4.4
0x1441a4  ldarg.0
0x1441a5  callvirt instance unsigned int32 Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance::get_LCID()
0x1441aa  box      [mscorlib]System.UInt32
0x1441af  stelem.ref
0x1441b0  dup
0x1441b1  ldc.i4.5
0x1441b2  ldarg.0
0x1441b3  callvirt instance valuetype TriState Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance::get_CaseSensitivity()
0x1441b8  stloc.0
0x1441b9  ldloca.s 0
0x1441bb  constrained. TriState
0x1441c1  callvirt instance string [mscorlib]System.Object::ToString()
0x1441c6  stelem.ref
0x1441c7  dup
0x1441c8  ldc.i4.6
0x1441c9  ldarg.0
0x1441ca  callvirt instance valuetype TriState Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance::get_AccentSensitivity()
0x1441cf  stloc.0
0x1441d0  ldloca.s 0
0x1441d2  constrained. TriState
0x1441d8  callvirt instance string [mscorlib]System.Object::ToString()
0x1441dd  stelem.ref
0x1441de  dup
0x1441df  ldc.i4.7
0x1441e0  ldarg.0
0x1441e1  callvirt instance valuetype TriState Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance::get_KanatypeSensitivity()
0x1441e6  stloc.0
0x1441e7  ldloca.s 0
0x1441e9  constrained. TriState
0x1441ef  callvirt instance string [mscorlib]System.Object::ToString()
0x1441f4  stelem.ref
0x1441f5  dup
0x1441f6  ldc.i4.8
0x1441f7  ldarg.0
0x1441f8  callvirt instance valuetype TriState Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance::get_WidthSensitivity()
0x1441fd  stloc.0
0x1441fe  ldloca.s 0
0x144200  constrained. TriState
0x144206  callvirt instance string [mscorlib]System.Object::ToString()
0x14420b  stelem.ref
0x14420c  dup
0x14420d  ldc.i4.s 9
0x14420f  ldarg.0
0x144210  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataSetInstance::get_RewrittenCommandText()
0x144215  stelem.ref
0x144216  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x14421b  ldarg.0
0x14421c  ldarg.1
0x14421d  call     void Microsoft.ReportingServices.ReportIntermediateFormat.GroupTreeTracer::TraceScopeInstance(class Microsoft.ReportingServices.ReportIntermediateFormat.ScopeInstance scopeInstance, int32 level)
0x144222  ret
```
