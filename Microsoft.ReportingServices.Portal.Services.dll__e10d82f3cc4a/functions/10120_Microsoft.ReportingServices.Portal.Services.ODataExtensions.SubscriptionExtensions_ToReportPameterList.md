# Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ToReportPameterList

- ea: `0x10120`
- end: `0x1018a`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ToReportPameterList`
- size: `106`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xfbf0`
- `0xfd90`
- `0x10190`

## callees

- `0xeb40`
- `0xeb80`
- `0x10120`

## pseudocode

```c

```

## disassembly

```asm
0x10120  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue>::.ctor()
0x10125  stloc.0
0x10126  ldarg.0
0x10127  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::m_parameters
0x1012c  stloc.1
0x1012d  ldc.i4.0
0x1012e  stloc.2
0x1012f  br.s     loc_10182
0x10131  ldloc.1
0x10132  ldloc.2
0x10133  ldelem.ref
0x10134  stloc.3
0x10135  ldloc.3
0x10136  isinst   [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ParameterValue
0x1013b  stloc.s  4
0x1013d  ldloc.s  4
0x1013f  brfalse.s loc_1016D
0x10141  ldarg.1
0x10142  ldloc.s  4
0x10144  ldfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ParameterValue::Name
0x10149  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType>::ContainsKey(var<u1>)
0x1014e  brfalse.s loc_1017E
0x10150  ldloc.0
0x10151  ldloc.s  4
0x10153  ldarg.1
0x10154  ldloc.s  4
0x10156  ldfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ParameterValue::Name
0x1015b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType>::get_Item(void)
0x10160  ldarg.2
0x10161  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue Microsoft.ReportingServices.Portal.Services.ODataExtensions.ParameterValueExtensions::ToWebApiReportParameterValue(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ParameterValue parameterValue, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType reportParameterType, string culture)
0x10166  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue>::Add(var<u1>)
0x1016b  br.s     loc_1017E
0x1016d  ldloc.0
0x1016e  ldloc.3
0x1016f  castclass [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ParameterFieldReference
0x10174  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue Microsoft.ReportingServices.Portal.Services.ODataExtensions.ParameterValueExtensions::ToWebApiReportParameterValue(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ParameterFieldReference parameterValue)
0x10179  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue>::Add(var<u1>)
0x1017e  ldloc.2
0x1017f  ldc.i4.1
0x10180  add
0x10181  stloc.2
0x10182  ldloc.2
0x10183  ldloc.1
0x10184  ldlen
0x10185  conv.i4
0x10186  blt.s    loc_10131
0x10188  ldloc.0
0x10189  ret
```
