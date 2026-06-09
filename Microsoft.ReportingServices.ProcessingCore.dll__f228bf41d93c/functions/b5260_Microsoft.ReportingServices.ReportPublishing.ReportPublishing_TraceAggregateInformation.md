# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::TraceAggregateInformation

- ea: `0xb5260`
- end: `0xb532d`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::TraceAggregateInformation`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xb5070`

## callees

- `0xb5260`
- `0xb5330`
- `0xef670`
- `0xef690`
- `0xef830`
- `0xef900`
- `0xefa20`
- `0xeffa0`
- `0x22ef20`
- `0x22ef40`

## string_xrefs

- `0xb528c`: `Aggregate Debugging Information (duplicate items removed):`
- `0xb52eb`: `    Aggregate: ContainingObject:{4} ContainingProperty:{5} Text:{0} UpdateScope:{1} OutputScope:{2} ResetScope:{3}`

## pseudocode

```c

```

## disassembly

```asm
0xb5260  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0xb5265  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0xb526a  brfalse.s loc_B5276
0xb526c  ldarg.1
0xb526d  callvirt instance valuetype AggregateTypes Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo::get_AggregateType()
0xb5272  ldc.i4.s 0xE
0xb5274  bne.un.s loc_B5277
0xb5276  ret
0xb5277  ldarg.0
0xb5278  ldfld    bool Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_wroteAggregateHeaderInformation
0xb527d  brtrue.s loc_B5296
0xb527f  ldarg.0
0xb5280  ldc.i4.1
0xb5281  stfld    bool Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_wroteAggregateHeaderInformation
0xb5286  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0xb528b  ldc.i4.4
0xb528c  ldstr    aAggregateDebug// "Aggregate Debugging Information (duplic"...
0xb5291  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xb5296  ldarg.0
0xb5297  ldarg.1
0xb5298  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.IRIFDataScope Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo::get_EvaluationScope()
0xb529d  call     instance string Microsoft.ReportingServices.ReportPublishing.ReportPublishing::GetScopeName(class Microsoft.ReportingServices.ReportIntermediateFormat.IRIFDataScope dataScope)
0xb52a2  stloc.0
0xb52a3  ldarg.1
0xb52a4  isinst   Microsoft.ReportingServices.ReportIntermediateFormat.RunningValueInfo
0xb52a9  stloc.2
0xb52aa  ldloc.2
0xb52ab  brfalse.s loc_B52B6
0xb52ad  ldloc.2
0xb52ae  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.RunningValueInfo::get_Scope()
0xb52b3  stloc.1
0xb52b4  br.s     loc_B52B8
0xb52b6  ldloc.0
0xb52b7  stloc.1
0xb52b8  ldarg.2
0xb52b9  brtrue.s loc_B52C9
0xb52bb  ldloc.0
0xb52bc  ldstr    aRow_0// "-ROW"
0xb52c1  call     string [mscorlib]System.String::Concat(string, string)
0xb52c6  stloc.3
0xb52c7  br.s     loc_B52E5
0xb52c9  ldarg.0
0xb52ca  ldarg.2
0xb52cb  call     instance string Microsoft.ReportingServices.ReportPublishing.ReportPublishing::GetScopeName(class Microsoft.ReportingServices.ReportIntermediateFormat.IRIFDataScope dataScope)
0xb52d0  stloc.3
0xb52d1  ldarg.1
0xb52d2  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo::get_UpdatesAtRowScope()
0xb52d7  brfalse.s loc_B52E5
0xb52d9  ldloc.3
0xb52da  ldstr    aRow_0// "-ROW"
0xb52df  call     string [mscorlib]System.String::Concat(string, string)
0xb52e4  stloc.3
0xb52e5  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0xb52ea  ldc.i4.4
0xb52eb  ldstr    aAggregateConta// "    Aggregate: ContainingObject:{4} Con"...
0xb52f0  ldc.i4.6
0xb52f1  newarr   [mscorlib]System.Object
0xb52f6  dup
0xb52f7  ldc.i4.0
0xb52f8  ldarg.1
0xb52f9  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo::GetAsString()
0xb52fe  stelem.ref
0xb52ff  dup
0xb5300  ldc.i4.1
0xb5301  ldloc.3
0xb5302  stelem.ref
0xb5303  dup
0xb5304  ldc.i4.2
0xb5305  ldloc.0
0xb5306  stelem.ref
0xb5307  dup
0xb5308  ldc.i4.3
0xb5309  ldloc.1
0xb530a  stelem.ref
0xb530b  dup
0xb530c  ldc.i4.4
0xb530d  ldarg.1
0xb530e  callvirt instance class PublishingValidationInfo Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo::get_PublishingInfo()
0xb5313  callvirt instance string PublishingValidationInfo::get_ObjectName()
0xb5318  stelem.ref
0xb5319  dup
0xb531a  ldc.i4.5
0xb531b  ldarg.1
0xb531c  callvirt instance class PublishingValidationInfo Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo::get_PublishingInfo()
0xb5321  callvirt instance string PublishingValidationInfo::get_PropertyName()
0xb5326  stelem.ref
0xb5327  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xb532c  ret
```
