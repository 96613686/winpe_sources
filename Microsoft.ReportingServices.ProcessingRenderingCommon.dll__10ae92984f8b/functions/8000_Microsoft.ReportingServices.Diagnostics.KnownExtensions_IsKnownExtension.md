# Microsoft.ReportingServices.Diagnostics.KnownExtensions::IsKnownExtension

- ea: `0x8000`
- end: `0x80ed`
- name: `Microsoft.ReportingServices.Diagnostics.KnownExtensions::IsKnownExtension`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x6b40`
- `0x80f0`

## callees

- `0x8000`
- `0x81b0`
- `0x81f0`

## string_xrefs

- `0x803d`: `Security`

## pseudocode

```c

```

## disassembly

```asm
0x8000  ldarg.2
0x8001  call     bool Microsoft.ReportingServices.Diagnostics.KnownExtensions::IsSqlSigned(string assemblyFullName)
0x8006  brtrue.s loc_800A
0x8008  ldc.i4.0
0x8009  ret
0x800a  ldarg.0
0x800b  ldstr    aData// "Data"
0x8010  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8015  brfalse.s loc_8023
0x8017  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.KnownExtensions::m_knownDataExtensions
0x801c  ldarg.1
0x801d  call     bool Microsoft.ReportingServices.Diagnostics.KnownExtensions::IsInList(class [mscorlib]System.Collections.Generic.List`1<string> list, string configTypeAndAssembly)
0x8022  ret
0x8023  ldarg.0
0x8024  ldstr    aAuthentication// "Authentication"
0x8029  call     bool [mscorlib]System.String::op_Equality(string, string)
0x802e  brfalse.s loc_803C
0x8030  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.KnownExtensions::m_knownAuthenticationExtensions
0x8035  ldarg.1
0x8036  call     bool Microsoft.ReportingServices.Diagnostics.KnownExtensions::IsInList(class [mscorlib]System.Collections.Generic.List`1<string> list, string configTypeAndAssembly)
0x803b  ret
0x803c  ldarg.0
0x803d  ldstr    aSecurity// "Security"
0x8042  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8047  brfalse.s loc_8055
0x8049  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.KnownExtensions::m_knownAuthorizationExtensions
0x804e  ldarg.1
0x804f  call     bool Microsoft.ReportingServices.Diagnostics.KnownExtensions::IsInList(class [mscorlib]System.Collections.Generic.List`1<string> list, string configTypeAndAssembly)
0x8054  ret
0x8055  ldarg.0
0x8056  ldstr    aSemanticquery// "SemanticQuery"
0x805b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8060  brfalse.s loc_806E
0x8062  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.KnownExtensions::m_knownSQExtensions
0x8067  ldarg.1
0x8068  call     bool Microsoft.ReportingServices.Diagnostics.KnownExtensions::IsInList(class [mscorlib]System.Collections.Generic.List`1<string> list, string configTypeAndAssembly)
0x806d  ret
0x806e  ldarg.0
0x806f  ldstr    aModelgeneratio// "ModelGeneration"
0x8074  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8079  brfalse.s loc_8087
0x807b  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.KnownExtensions::m_knownModelGenExtensions
0x8080  ldarg.1
0x8081  call     bool Microsoft.ReportingServices.Diagnostics.KnownExtensions::IsInList(class [mscorlib]System.Collections.Generic.List`1<string> list, string configTypeAndAssembly)
0x8086  ret
0x8087  ldarg.0
0x8088  ldstr    aDelivery// "Delivery"
0x808d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8092  brfalse.s loc_80A0
0x8094  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.KnownExtensions::m_knownDeliveryExtensions
0x8099  ldarg.1
0x809a  call     bool Microsoft.ReportingServices.Diagnostics.KnownExtensions::IsInList(class [mscorlib]System.Collections.Generic.List`1<string> list, string configTypeAndAssembly)
0x809f  ret
0x80a0  ldarg.0
0x80a1  ldstr    aRender// "Render"
0x80a6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x80ab  brfalse.s loc_80B9
0x80ad  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.KnownExtensions::m_knownRenderingExtensions
0x80b2  ldarg.1
0x80b3  call     bool Microsoft.ReportingServices.Diagnostics.KnownExtensions::IsInList(class [mscorlib]System.Collections.Generic.List`1<string> list, string configTypeAndAssembly)
0x80b8  ret
0x80b9  ldarg.0
0x80ba  ldstr    aEventprocessin// "EventProcessing"
0x80bf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x80c4  brfalse.s loc_80D2
0x80c6  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.KnownExtensions::m_knownEventExtensions
0x80cb  ldarg.1
0x80cc  call     bool Microsoft.ReportingServices.Diagnostics.KnownExtensions::IsInList(class [mscorlib]System.Collections.Generic.List`1<string> list, string configTypeAndAssembly)
0x80d1  ret
0x80d2  ldarg.0
0x80d3  ldstr    aReportdefiniti// "ReportDefinitionCustomization"
0x80d8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x80dd  brfalse.s loc_80EB
0x80df  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.KnownExtensions::m_knownReportDefinitionCustomizationExtensions
0x80e4  ldarg.1
0x80e5  call     bool Microsoft.ReportingServices.Diagnostics.KnownExtensions::IsInList(class [mscorlib]System.Collections.Generic.List`1<string> list, string configTypeAndAssembly)
0x80ea  ret
0x80eb  ldc.i4.0
0x80ec  ret
```
