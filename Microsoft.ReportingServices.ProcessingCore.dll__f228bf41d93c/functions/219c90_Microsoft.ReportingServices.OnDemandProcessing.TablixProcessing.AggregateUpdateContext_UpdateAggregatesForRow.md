# Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.AggregateUpdateContext::UpdateAggregatesForRow

- ea: `0x219c90`
- end: `0x219d08`
- name: `Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.AggregateUpdateContext::UpdateAggregatesForRow`
- size: `120`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x212bb0`
- `0x21ae20`
- `0x21d370`

## callees

- `0xf0f50`
- `0x219c90`
- `0x21acf0`

## string_xrefs

- `0x219ca9`: `UpdateAggregatesForRow must be driven by a call to UpdateAggregates.`

## pseudocode

```c

```

## disassembly

```asm
0x219c90  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x219c95  ldarg.0
0x219c96  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj> Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.AggregateUpdateContext::m_aggsForUpdateAtRowScope
0x219c9b  brtrue.s loc_219CA8
0x219c9d  ldarg.0
0x219c9e  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.AggregateUpdateContext::m_runningValuesForUpdateAtRow
0x219ca3  ldnull
0x219ca4  cgt.un
0x219ca6  br.s     loc_219CA9
0x219ca8  ldc.i4.1
0x219ca9  ldstr    aUpdateaggregat// "UpdateAggregatesForRow must be driven b"...
0x219cae  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x219cb3  ldarg.0
0x219cb4  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj> Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.AggregateUpdateContext::m_aggsForUpdateAtRowScope
0x219cb9  brfalse.s loc_219CEE
0x219cbb  ldarg.0
0x219cbc  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj> Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.AggregateUpdateContext::m_aggsForUpdateAtRowScope
0x219cc1  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj>::GetEnumerator()
0x219cc6  stloc.0
0x219cc7  br.s     loc_219CD5
0x219cc9  ldloca.s 0
0x219ccb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj>::get_Current()
0x219cd0  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj::Update()
0x219cd5  ldloca.s 0
0x219cd7  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj>::MoveNext()
0x219cdc  brtrue.s loc_219CC9
0x219cde  leave.s  loc_219CEE
0x219ce0  ldloca.s 0
0x219ce2  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateObj>
0x219ce8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x219ced  endfinally
0x219cee  ldarg.0
0x219cef  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.AggregateUpdateContext::m_runningValuesForUpdateAtRow
0x219cf4  brfalse.s loc_219D07
0x219cf6  ldarg.0
0x219cf7  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.AggregateUpdateContext::m_odpContext
0x219cfc  ldarg.0
0x219cfd  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.AggregateUpdateContext::m_runningValuesForUpdateAtRow
0x219d02  call     void Microsoft.ReportingServices.OnDemandProcessing.TablixProcessing.RuntimeDataTablixObj::UpdateRunningValues(class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext odpContext, class [mscorlib]System.Collections.Generic.List`1<string> runningValueNames)
0x219d07  ret
```
