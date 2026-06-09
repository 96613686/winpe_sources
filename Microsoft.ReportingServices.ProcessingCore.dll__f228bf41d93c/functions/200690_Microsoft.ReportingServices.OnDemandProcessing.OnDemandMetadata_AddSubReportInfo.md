# Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::AddSubReportInfo

- ea: `0x200690`
- end: `0x20072a`
- name: `Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::AddSubReportInfo`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x179460`

## callees

- `0xda6a0`
- `0xda6c0`
- `0xda6d0`
- `0xda6e0`
- `0xdaa40`
- `0xdaac0`
- `0x200690`
- `0x200730`

## string_xrefs

- `0x2006c3`: `(!m_subReportInfoMap.ContainsKey(definitionPath))`

## pseudocode

```c

```

## disassembly

```asm
0x200690  ldarg.0
0x200691  ldc.i4.1
0x200692  stfld    bool Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::m_metaDataChanged
0x200697  ldarg.0
0x200698  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInfo> Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::m_subReportInfoMap
0x20069d  brtrue.s loc_2006AF
0x20069f  ldarg.0
0x2006a0  ldsfld   class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string> Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.EqualityComparers::StringComparerInstance
0x2006a5  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInfo>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x2006aa  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInfo> Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::m_subReportInfoMap
0x2006af  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x2006b4  ldarg.0
0x2006b5  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInfo> Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::m_subReportInfoMap
0x2006ba  ldarg.2
0x2006bb  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInfo>::ContainsKey(var<u1>)
0x2006c0  ldc.i4.0
0x2006c1  ceq
0x2006c3  ldstr    aMSubreportinfo// "(!m_subReportInfoMap.ContainsKey(defini"...
0x2006c8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x2006cd  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x2006d2  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInfo::.ctor(valuetype [mscorlib]System.Guid uniqueName)
0x2006d7  stloc.0
0x2006d8  ldarg.0
0x2006d9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInfo> Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::m_subReportInfoMap
0x2006de  ldarg.2
0x2006df  ldloc.0
0x2006e0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInfo>::Add(var<u1>, !!T0)
0x2006e5  ldarg.1
0x2006e6  brtrue.s loc_2006F6
0x2006e8  ldarg.2
0x2006e9  ldstr    asc_2827E0// "_"
0x2006ee  ldarg.3
0x2006ef  call     string [mscorlib]System.String::Concat(string, string, string)
0x2006f4  br.s     loc_2006F7
0x2006f6  ldarg.3
0x2006f7  stloc.2
0x2006f8  ldloc.0
0x2006f9  ldarg.0
0x2006fa  ldloc.2
0x2006fb  ldloca.s 1
0x2006fd  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo Microsoft.ReportingServices.OnDemandProcessing.OnDemandMetadata::GetOrCreateCommonSubReportInfo(string reportPath, [out] bool& created)
0x200702  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInfo::set_CommonSubReportInfo(class Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo value)
0x200707  ldloc.1
0x200708  brfalse.s loc_200728
0x20070a  ldloc.0
0x20070b  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInfo::get_CommonSubReportInfo()
0x200710  ldloc.0
0x200711  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInfo::get_UniqueName()
0x200716  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo::set_DefinitionUniqueName(string value)
0x20071b  ldloc.0
0x20071c  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo Microsoft.ReportingServices.ReportIntermediateFormat.SubReportInfo::get_CommonSubReportInfo()
0x200721  ldarg.s  4
0x200723  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.CommonSubReportInfo::set_OriginalCatalogPath(string value)
0x200728  ldloc.0
0x200729  ret
```
