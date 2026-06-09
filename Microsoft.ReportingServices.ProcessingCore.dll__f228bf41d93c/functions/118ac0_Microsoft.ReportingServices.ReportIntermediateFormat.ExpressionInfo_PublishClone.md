# Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::PublishClone

- ea: `0x118ac0`
- end: `0x11964a`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::PublishClone`
- size: `2954`
- prototype: ``
- caller_count: `133`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0xc4290`
- `0xc49f0`
- `0xc4f90`
- `0xc5380`
- `0xc57c0`
- `0xc5ba0`
- `0xc5e10`
- `0xc6190`
- `0xc67f0`
- `0xc7160`
- `0xc75c0`
- `0xc79c0`
- `0xc7ee0`
- `0xc85d0`
- `0xc9170`
- `0xcafb0`
- `0xcbb60`
- `0xcc740`
- `0xcd200`
- `0xcd570`
- `0xcda50`
- `0xce4f0`
- `0xcf520`
- `0xcfa90`
- `0xd01d0`
- `0xd0d80`
- `0xd1360`
- `0xd1b00`
- `0xd1e60`
- `0xd27b0`
- `0xd3620`
- `0xd3f80`
- `0xd4c70`
- `0xd57a0`
- `0xdb370`
- `0xdd1a0`
- `0xdd6a0`
- `0xddf50`
- `0xde480`
- `0xde870`
- `0xdf010`
- `0xdf7b0`
- `0xdff50`
- `0xe01f0`
- `0xe05a0`
- `0xe0bb0`
- `0xe1350`
- `0xe1990`
- `0xe1e00`
- `0xe29f0`

## callees

- `0x8da00`
- `0x8dcf0`
- `0x8dd10`
- `0x8df40`
- `0xef630`
- `0xef920`
- `0xefa20`
- `0x117c60`
- `0x118ac0`
- `0x119a30`
- `0x11c3e0`
- `0x11c450`
- `0x11c520`
- `0x22f5c0`

## pseudocode

```c

```

## disassembly

```asm
0x118ac0  ldarg.0
0x118ac1  call     instance object [mscorlib]System.Object::MemberwiseClone()
0x118ac6  castclass Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo
0x118acb  stloc.0
0x118acc  ldarg.0
0x118acd  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.RdlFunctionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_RdlFunctionInfo()
0x118ad2  brfalse  loc_118B98
0x118ad7  ldloc.0
0x118ad8  ldarg.0
0x118ad9  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.RdlFunctionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_rdlFunctionInfo
0x118ade  ldarg.1
0x118adf  callvirt instance object Microsoft.ReportingServices.ReportIntermediateFormat.RdlFunctionInfo::PublishClone(valuetype Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext context)
0x118ae4  castclass Microsoft.ReportingServices.ReportIntermediateFormat.RdlFunctionInfo
0x118ae9  stfld    class Microsoft.ReportingServices.ReportIntermediateFormat.RdlFunctionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_rdlFunctionInfo
0x118aee  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x118af3  ldarg.0
0x118af4  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_aggregates
0x118af9  ldnull
0x118afa  ceq
0x118afc  ldstr    aThisMAggregate// "this.m_aggregates == null"
0x118b01  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x118b06  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x118b0b  ldarg.0
0x118b0c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.RunningValueInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_runningValues
0x118b11  ldnull
0x118b12  ceq
0x118b14  ldstr    aThisMAggregate// "this.m_aggregates == null"
0x118b19  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x118b1e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x118b23  ldarg.0
0x118b24  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_lookups
0x118b29  ldnull
0x118b2a  ceq
0x118b2c  ldstr    aThisMAggregate// "this.m_aggregates == null"
0x118b31  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x118b36  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x118b3b  ldarg.0
0x118b3c  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_referencedReportItems
0x118b41  ldnull
0x118b42  ceq
0x118b44  ldstr    aThisMAggregate// "this.m_aggregates == null"
0x118b49  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x118b4e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x118b53  ldarg.0
0x118b54  ldfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_referencedReportItemPositionsInOriginalText
0x118b59  ldnull
0x118b5a  ceq
0x118b5c  ldstr    aThisMAggregate// "this.m_aggregates == null"
0x118b61  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x118b66  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x118b6b  ldarg.0
0x118b6c  ldfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_meDotValuePositionsInOriginalText
0x118b71  ldnull
0x118b72  ceq
0x118b74  ldstr    aThisMAggregate// "this.m_aggregates == null"
0x118b79  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x118b7e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x118b83  ldarg.0
0x118b84  ldfld    string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_transformedExpression
0x118b89  ldnull
0x118b8a  ceq
0x118b8c  ldstr    aThisMAggregate// "this.m_aggregates == null"
0x118b91  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x118b96  ldloc.0
0x118b97  ret
0x118b98  ldarg.0
0x118b99  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_aggregates
0x118b9e  brfalse.s loc_118BFC
0x118ba0  ldloc.0
0x118ba1  ldarg.0
0x118ba2  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_aggregates
0x118ba7  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo>::get_Count()
0x118bac  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo>::.ctor(int32)
0x118bb1  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_aggregates
0x118bb6  ldarg.0
0x118bb7  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_aggregates
0x118bbc  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo>::GetEnumerator()
0x118bc1  stloc.1
0x118bc2  br.s     loc_118BE3
0x118bc4  ldloca.s 1
0x118bc6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo>::get_Current()
0x118bcb  stloc.2
0x118bcc  ldloc.0
0x118bcd  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_aggregates
0x118bd2  ldloc.2
0x118bd3  ldarg.1
0x118bd4  callvirt instance object Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo::PublishClone(valuetype Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext context)
0x118bd9  castclass Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo
0x118bde  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo>::Add(var<u1>)
0x118be3  ldloca.s 1
0x118be5  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo>::MoveNext()
0x118bea  brtrue.s loc_118BC4
0x118bec  leave.s  loc_118BFC
0x118bee  ldloca.s 1
0x118bf0  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo>
0x118bf6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x118bfb  endfinally
0x118bfc  ldarg.0
0x118bfd  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.RunningValueInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_runningValues
0x118c02  brfalse.s loc_118C62
0x118c04  ldloc.0
0x118c05  ldarg.0
0x118c06  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.RunningValueInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_runningValues
0x118c0b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.RunningValueInfo>::get_Count()
0x118c10  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.RunningValueInfo>::.ctor(int32)
0x118c15  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.RunningValueInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_runningValues
0x118c1a  ldarg.0
0x118c1b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.RunningValueInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_runningValues
0x118c20  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.RunningValueInfo>::GetEnumerator()
0x118c25  stloc.3
0x118c26  br.s     loc_118C49
0x118c28  ldloca.s 3
0x118c2a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.ReportIntermediateFormat.RunningValueInfo>::get_Current()
0x118c2f  stloc.s  4
0x118c31  ldloc.0
0x118c32  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.RunningValueInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_runningValues
0x118c37  ldloc.s  4
0x118c39  ldarg.1
0x118c3a  callvirt instance object Microsoft.ReportingServices.ReportIntermediateFormat.DataAggregateInfo::PublishClone(valuetype Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext context)
0x118c3f  castclass Microsoft.ReportingServices.ReportIntermediateFormat.RunningValueInfo
0x118c44  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.RunningValueInfo>::Add(var<u1>)
0x118c49  ldloca.s 3
0x118c4b  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.ReportIntermediateFormat.RunningValueInfo>::MoveNext()
0x118c50  brtrue.s loc_118C28
0x118c52  leave.s  loc_118C62
0x118c54  ldloca.s 3
0x118c56  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.ReportIntermediateFormat.RunningValueInfo>
0x118c5c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x118c61  endfinally
0x118c62  ldarg.0
0x118c63  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_lookups
0x118c68  brfalse.s loc_118CC9
0x118c6a  ldloc.0
0x118c6b  ldarg.0
0x118c6c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_lookups
0x118c71  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo>::get_Count()
0x118c76  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo>::.ctor(int32)
0x118c7b  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_lookups
0x118c80  ldarg.0
0x118c81  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_lookups
0x118c86  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo>::GetEnumerator()
0x118c8b  stloc.s  5
0x118c8d  br.s     loc_118CB0
0x118c8f  ldloca.s 5
0x118c91  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo>::get_Current()
0x118c96  stloc.s  6
0x118c98  ldloc.0
0x118c99  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_lookups
0x118c9e  ldloc.s  6
0x118ca0  ldarg.1
0x118ca1  callvirt instance object Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo::PublishClone(valuetype Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext context)
0x118ca6  castclass Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo
0x118cab  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo>::Add(var<u1>)
0x118cb0  ldloca.s 5
0x118cb2  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo>::MoveNext()
0x118cb7  brtrue.s loc_118C8F
0x118cb9  leave.s  loc_118CC9
0x118cbb  ldloca.s 5
0x118cbd  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo>
0x118cc3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x118cc8  endfinally
0x118cc9  ldarg.0
0x118cca  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_referencedReportItems
0x118ccf  brfalse.s loc_118D37
0x118cd1  ldloc.0
0x118cd2  ldarg.0
0x118cd3  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_referencedReportItems
0x118cd8  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x118cdd  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(int32)
0x118ce2  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_referencedReportItems
0x118ce7  ldarg.0
0x118ce8  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_referencedReportItems
0x118ced  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x118cf2  stloc.s  7
0x118cf4  br.s     loc_118D16
0x118cf6  ldloca.s 7
0x118cf8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x118cfd  stloc.s  8
0x118cff  ldloc.0
0x118d00  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_referencedReportItems
0x118d05  ldloc.s  8
0x118d07  callvirt instance object [mscorlib]System.String::Clone()
0x118d0c  castclass [mscorlib]System.String
0x118d11  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x118d16  ldloca.s 7
0x118d18  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x118d1d  brtrue.s loc_118CF6
0x118d1f  leave.s  loc_118D2F
0x118d21  ldloca.s 7
0x118d23  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x118d29  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x118d2e  endfinally
0x118d2f  ldarga.s 1
0x118d31  ldloc.0
0x118d32  call     instance void Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext::AddExpressionThatReferencesReportItems(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression)
0x118d37  ldarg.0
0x118d38  ldfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_referencedReportItemPositionsInOriginalText
0x118d3d  brfalse.s loc_118D93
0x118d3f  ldloc.0
0x118d40  ldarg.0
0x118d41  ldfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_referencedReportItemPositionsInOriginalText
0x118d46  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0x118d4b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor(int32)
0x118d50  stfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_referencedReportItemPositionsInOriginalText
0x118d55  ldarg.0
0x118d56  ldfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_referencedReportItemPositionsInOriginalText
0x118d5b  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<int32>::GetEnumerator()
0x118d60  stloc.s  9
0x118d62  br.s     loc_118D7A
0x118d64  ldloca.s 9
0x118d66  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>::get_Current()
0x118d6b  stloc.s  0xA
0x118d6d  ldloc.0
0x118d6e  ldfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_referencedReportItemPositionsInOriginalText
0x118d73  ldloc.s  0xA
0x118d75  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x118d7a  ldloca.s 9
0x118d7c  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>::MoveNext()
0x118d81  brtrue.s loc_118D64
0x118d83  leave.s  loc_118D93
0x118d85  ldloca.s 9
0x118d87  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>
0x118d8d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x118d92  endfinally
0x118d93  ldarg.0
0x118d94  ldfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_meDotValuePositionsInOriginalText
0x118d99  brfalse.s loc_118DEF
0x118d9b  ldloc.0
0x118d9c  ldarg.0
0x118d9d  ldfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_meDotValuePositionsInOriginalText
0x118da2  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0x118da7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor(int32)
0x118dac  stfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_meDotValuePositionsInOriginalText
0x118db1  ldarg.0
0x118db2  ldfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_meDotValuePositionsInOriginalText
0x118db7  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<int32>::GetEnumerator()
0x118dbc  stloc.s  9
0x118dbe  br.s     loc_118DD6
0x118dc0  ldloca.s 9
0x118dc2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>::get_Current()
0x118dc7  stloc.s  0xB
0x118dc9  ldloc.0
0x118dca  ldfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_meDotValuePositionsInOriginalText
0x118dcf  ldloc.s  0xB
0x118dd1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x118dd6  ldloca.s 9
0x118dd8  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>::MoveNext()
0x118ddd  brtrue.s loc_118DC0
0x118ddf  leave.s  loc_118DEF
0x118de1  ldloca.s 9
0x118de3  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int32>
0x118de9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x118dee  endfinally
0x118def  ldarg.0
0x118df0  ldfld    string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_transformedExpression
0x118df5  brfalse  loc_119575
0x118dfa  ldarg.0
0x118dfb  ldfld    string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_transformedExpression
0x118e00  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x118e05  stloc.s  0xC
0x118e07  ldnull
0x118e08  stloc.s  0xD
0x118e0a  ldc.i4.0
0x118e0b  stloc.s  0xE
0x118e0d  ldc.i4.0
0x118e0e  stloc.s  0xF
0x118e10  ldc.i4.0
0x118e11  stloc.s  0x10
0x118e13  ldc.i4.0
0x118e14  stloc.s  0x11
0x118e16  ldc.i4.0
0x118e17  stloc.s  0x12
0x118e19  ldarg.0
0x118e1a  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TransformedExprSpecialFunctionInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_transformedExprAggregateInfos
0x118e1f  brfalse.s loc_118E93
0x118e21  ldloc.0
0x118e22  ldarg.0
0x118e23  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TransformedExprSpecialFunctionInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_transformedExprAggregateInfos
0x118e28  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class TransformedExprSpecialFunctionInfo>::get_Count()
0x118e2d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class TransformedExprSpecialFunctionInfo>::.ctor(int32)
0x118e32  stfld    class [mscorlib]System.Collections.Generic.List`1<class TransformedExprSpecialFunctionInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_transformedExprAggregateInfos
0x118e37  ldarg.0
0x118e38  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TransformedExprSpecialFunctionInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_transformedExprAggregateInfos
0x118e3d  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class TransformedExprSpecialFunctionInfo>::GetEnumerator()
0x118e42  stloc.s  0x1F
0x118e44  br.s     loc_118E67
0x118e46  ldloca.s 0x1F
0x118e48  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class TransformedExprSpecialFunctionInfo>::get_Current()
0x118e4d  stloc.s  0x20
0x118e4f  ldloc.0
0x118e50  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TransformedExprSpecialFunctionInfo> Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::m_transformedExprAggregateInfos
0x118e55  ldloc.s  0x20
0x118e57  ldarg.1
0x118e58  callvirt instance object TransformedExprSpecialFunctionInfo::PublishClone(valuetype Microsoft.ReportingServices.ReportPublishing.AutomaticSubtotalContext context)
0x118e5d  castclass TransformedExprSpecialFunctionInfo
0x118e62  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TransformedExprSpecialFunctionInfo>::Add(var<u1>)
0x118e67  ldloca.s 0x1F
0x118e69  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class TransformedExprSpecialFunctionInfo>::MoveNext()
0x118e6e  brtrue.s loc_118E46
0x118e70  leave.s  loc_118E80
  ... truncated ...
```
