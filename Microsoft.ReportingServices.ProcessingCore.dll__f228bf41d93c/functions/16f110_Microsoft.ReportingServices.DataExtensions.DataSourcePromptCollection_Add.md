# Microsoft.ReportingServices.DataExtensions.DataSourcePromptCollection::Add

- ea: `0x16f110`
- end: `0x16f159`
- name: `Microsoft.ReportingServices.DataExtensions.DataSourcePromptCollection::Add`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x16ef80`

## callees

- `0x16f110`
- `0x16fca0`
- `0x1702d0`
- `0x170390`

## string_xrefs

- `0x16f12b`: `Collection already contains this data source.`

## pseudocode

```c

```

## disassembly

```asm
0x16f110  ldarg.1
0x16f111  callvirt instance string Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_OriginalName()
0x16f116  stloc.0
0x16f117  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x16f11c  ldarg.0
0x16f11d  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.DataExtensions.DataSourcePromptCollection::m_collection
0x16f122  ldloc.0
0x16f123  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x16f128  ldnull
0x16f129  ceq
0x16f12b  ldstr    aCollectionAlre// "Collection already contains this data s"...
0x16f130  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x16f135  ldarg.1
0x16f136  ldarg.2
0x16f137  callvirt instance void Microsoft.ReportingServices.DataExtensions.DataSourceInfo::ThrowIfNotUsable(class Microsoft.ReportingServices.DataExtensions.ServerDataSourceSettings serverDatasourceSetting)
0x16f13c  ldarg.0
0x16f13d  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.DataExtensions.DataSourcePromptCollection::m_collection
0x16f142  ldloc.0
0x16f143  ldarg.1
0x16f144  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x16f149  ldarg.1
0x16f14a  callvirt instance bool Microsoft.ReportingServices.DataExtensions.DataSourceInfo::get_NeedPrompt()
0x16f14f  brfalse.s loc_16F158
0x16f151  ldarg.0
0x16f152  ldc.i4.1
0x16f153  stfld    bool Microsoft.ReportingServices.DataExtensions.DataSourcePromptCollection::m_needPrompt
0x16f158  ret
```
