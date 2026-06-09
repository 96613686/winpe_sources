# Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteRestartTokens

- ea: `0x16c900`
- end: `0x16c9c1`
- name: `Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteRestartTokens`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x16c9d0`

## callees

- `0x274d0`
- `0x27db0`
- `0xc3d50`
- `0xc3d60`
- `0x16c1f0`
- `0x16c200`
- `0x16c210`
- `0x16c240`
- `0x16c900`
- `0x173720`
- `0x173b00`
- `0x173b40`
- `0x173d40`

## string_xrefs

- `0x16c90a`: `RestartTokens`

## pseudocode

```c

```

## disassembly

```asm
0x16c900  ldarg.1
0x16c901  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.RestartDefinition>::get_Count()
0x16c906  brtrue.s loc_16C909
0x16c908  ret
0x16c909  ldarg.0
0x16c90a  ldstr    aRestarttokens// "RestartTokens"
0x16c90f  callvirt instance void Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WritePropertyName(string name)
0x16c914  ldarg.0
0x16c915  callvirt instance void Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteCollectionStart()
0x16c91a  ldarg.1
0x16c91b  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.RestartDefinition>::GetEnumerator()
0x16c920  stloc.0
0x16c921  br.s     loc_16C99E
0x16c923  ldloca.s 0
0x16c925  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.ReportIntermediateFormat.RestartDefinition>::get_Current()
0x16c92a  stloc.1
0x16c92b  ldarg.0
0x16c92c  callvirt instance void Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteCollectionStart()
0x16c931  ldloc.1
0x16c932  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.RestartDefinition::get_IsTotal()
0x16c937  brfalse.s loc_16C947
0x16c939  ldarg.0
0x16c93a  ldc.i4.0
0x16c93b  box      [mscorlib]System.Boolean
0x16c940  callvirt instance void Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteVariantValue(object value)
0x16c945  br.s     loc_16C998
0x16c947  ldarg.0
0x16c948  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.ReportIntermediateFormat.DataShapeMember, class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeMember> Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::m_restartMemberMapping
0x16c94d  ldloc.1
0x16c94e  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.DataShapeMember Microsoft.ReportingServices.ReportIntermediateFormat.RestartDefinition::get_DataMember()
0x16c953  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.ReportIntermediateFormat.DataShapeMember, class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeMember>::get_Item(void)
0x16c958  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.DataShapeMemberInstance Microsoft.ReportingServices.OnDemandReportRendering.DataShapeMember::get_Instance()
0x16c95d  castclass Microsoft.ReportingServices.OnDemandReportRendering.DataShapeDynamicMemberInstance
0x16c962  callvirt instance class Microsoft.ReportingServices.Common.ScopeID Microsoft.ReportingServices.OnDemandReportRendering.DataShapeDynamicMemberInstance::GetLastScopeID()
0x16c967  stloc.2
0x16c968  ldloc.2
0x16c969  ldnull
0x16c96a  call     bool Microsoft.ReportingServices.Common.ScopeID::op_Inequality(class Microsoft.ReportingServices.Common.ScopeID scopeID1, class Microsoft.ReportingServices.Common.ScopeID scopeID2)
0x16c96f  brfalse.s loc_16C998
0x16c971  ldc.i4.0
0x16c972  stloc.3
0x16c973  br.s     loc_16C98F
0x16c975  ldloc.2
0x16c976  ldloc.3
0x16c977  callvirt instance class Microsoft.ReportingServices.Common.ScopeValue Microsoft.ReportingServices.Common.ScopeID::GetScopeValue(int32 index)
0x16c97c  stloc.s  4
0x16c97e  ldarg.0
0x16c97f  ldloc.s  4
0x16c981  callvirt instance object Microsoft.ReportingServices.Common.SerializableValue::get_Value()
0x16c986  callvirt instance void Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteVariantValue(object value)
0x16c98b  ldloc.3
0x16c98c  ldc.i4.1
0x16c98d  add
0x16c98e  stloc.3
0x16c98f  ldloc.3
0x16c990  ldloc.2
0x16c991  callvirt instance int32 Microsoft.ReportingServices.Common.ScopeID::get_ScopeValueCount()
0x16c996  blt.s    loc_16C975
0x16c998  ldarg.0
0x16c999  callvirt instance void Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteCollectionEnd()
0x16c99e  ldloca.s 0
0x16c9a0  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.ReportIntermediateFormat.RestartDefinition>::MoveNext()
0x16c9a5  brtrue   loc_16C923
0x16c9aa  leave.s  loc_16C9BA
0x16c9ac  ldloca.s 0
0x16c9ae  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.ReportIntermediateFormat.RestartDefinition>
0x16c9b4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16c9b9  endfinally
0x16c9ba  ldarg.0
0x16c9bb  callvirt instance void Microsoft.ReportingServices.DataShapeResultRenderer.DataShapeResultWriter::WriteCollectionEnd()
0x16c9c0  ret
```
