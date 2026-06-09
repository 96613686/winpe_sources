# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ResolveKpiProperties

- ea: `0x4260`
- end: `0x4542`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ResolveKpiProperties`
- size: `738`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x37a0`
- `0x1dc70`

## callees

- `0x4260`
- `0x4550`
- `0x45a0`

## string_xrefs

- `0x4397`: `DrillthroughTarget.Path`
- `0x4489`: `KPI link catalog item unsuported.`

## pseudocode

```c

```

## disassembly

```asm
0x4260  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::.ctor()
0x4265  dup
0x4266  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x426b  dup
0x426c  ldstr    aDescription// "Description"
0x4271  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x4276  dup
0x4277  ldarg.1
0x4278  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Description()
0x427d  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x4282  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x4287  dup
0x4288  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x428d  dup
0x428e  ldstr    aHidden// "Hidden"
0x4293  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x4298  dup
0x4299  ldarg.1
0x429a  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Hidden()
0x429f  brtrue.s loc_42A8
0x42a1  ldstr    aFalse// "false"
0x42a6  br.s     loc_42AD
0x42a8  ldstr    aTrue// "true"
0x42ad  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x42b2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x42b7  dup
0x42b8  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x42bd  dup
0x42be  ldstr    aValueformat// "ValueFormat"
0x42c3  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x42c8  dup
0x42c9  ldarg.1
0x42ca  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiValueFormat [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::get_ValueFormat()
0x42cf  stloc.2
0x42d0  ldloca.s 2
0x42d2  call     instance string [mscorlib]System.Int32::ToString()
0x42d7  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x42dc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x42e1  dup
0x42e2  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x42e7  dup
0x42e8  ldstr    aVisualization// "Visualization"
0x42ed  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x42f2  dup
0x42f3  ldarg.1
0x42f4  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiVisualization [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::get_Visualization()
0x42f9  stloc.2
0x42fa  ldloca.s 2
0x42fc  call     instance string [mscorlib]System.Int32::ToString()
0x4301  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x4306  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x430b  dup
0x430c  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x4311  dup
0x4312  ldstr    aCurrency// "Currency"
0x4317  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x431c  dup
0x431d  ldarg.1
0x431e  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::get_Currency()
0x4323  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x4328  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x432d  stloc.0
0x432e  ldarg.1
0x432f  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTarget [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::get_DrillthroughTarget()
0x4334  brtrue   loc_43EC
0x4339  ldloc.0
0x433a  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x433f  dup
0x4340  ldstr    aDrillthroughta// "DrillthroughTarget.Type"
0x4345  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x434a  dup
0x434b  ldnull
0x434c  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x4351  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x4356  ldloc.0
0x4357  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x435c  dup
0x435d  ldstr    aDrillthroughta_0// "DrillthroughTarget.Url"
0x4362  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x4367  dup
0x4368  ldnull
0x4369  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x436e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x4373  ldloc.0
0x4374  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x4379  dup
0x437a  ldstr    aDrillthroughta_3// "DrillthroughTarget.CatalogItemType"
0x437f  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x4384  dup
0x4385  ldnull
0x4386  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x438b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x4390  ldloc.0
0x4391  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x4396  dup
0x4397  ldstr    aDrillthroughta_4// "DrillthroughTarget.Path"
0x439c  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x43a1  dup
0x43a2  ldnull
0x43a3  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x43a8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x43ad  ldloc.0
0x43ae  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x43b3  dup
0x43b4  ldstr    aDrillthroughta_5// "DrillthroughTarget.Id"
0x43b9  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x43be  dup
0x43bf  ldnull
0x43c0  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x43c5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x43ca  ldloc.0
0x43cb  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x43d0  dup
0x43d1  ldstr    aDrillthroughta_6// "DrillthroughTarget.Parameters"
0x43d6  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x43db  dup
0x43dc  ldnull
0x43dd  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x43e2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x43e7  br       loc_4499
0x43ec  ldarg.1
0x43ed  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTarget [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::get_DrillthroughTarget()
0x43f2  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTargetType [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTarget::get_Type()
0x43f7  brtrue   loc_4482
0x43fc  ldarg.1
0x43fd  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DrillthroughTarget [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::get_DrillthroughTarget()
0x4402  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.UrlDrillthroughTarget
0x4407  stloc.3
0x4408  ldloc.0
0x4409  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x440e  dup
0x440f  ldstr    aDrillthroughta// "DrillthroughTarget.Type"
0x4414  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x4419  dup
0x441a  ldc.i4.0
0x441b  stloc.2
0x441c  ldloca.s 2
0x441e  call     instance string [mscorlib]System.Int32::ToString()
0x4423  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x4428  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x442d  ldloc.0
0x442e  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x4433  dup
0x4434  ldstr    aDrillthroughta_0// "DrillthroughTarget.Url"
0x4439  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x443e  dup
0x443f  ldarg.0
0x4440  ldloc.3
0x4441  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.UrlDrillthroughTarget::get_Url()
0x4446  call     instance string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ValidateDrillthroughTargetUrl(string url)
0x444b  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x4450  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x4455  ldloc.0
0x4456  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x445b  dup
0x445c  ldstr    aDrillthroughta_1// "DrillthroughTarget.DirectNavigation"
0x4461  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x4466  dup
0x4467  ldloc.3
0x4468  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.UrlDrillthroughTarget::get_DirectNavigation()
0x446d  stloc.s  4
0x446f  ldloca.s 4
0x4471  call     instance string [mscorlib]System.Boolean::ToString()
0x4476  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x447b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x4480  br.s     loc_4499
0x4482  ldarg.0
0x4483  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x4488  ldc.i4.3
0x4489  ldstr    aKpiLinkCatalog// "KPI link catalog item unsuported."
0x448e  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4493  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0x4498  throw
0x4499  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfoCollection::.ctor()
0x449e  stloc.1
0x449f  ldstr    aValue// "Value"
0x44a4  ldarg.1
0x44a5  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiData [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::get_Data()
0x44aa  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiData::get_Value()
0x44af  ldarg.1
0x44b0  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiValues [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::get_Values()
0x44b5  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiValues::get_Value()
0x44ba  ldarg.2
0x44bb  ldloc.0
0x44bc  ldloc.1
0x44bd  call     void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ResolveKpiDataItemProperties(string dataItemName, class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem kpiDataItem, object value, class Microsoft.ReportingServices.Portal.Services.Extensions.ResolveCatalogItem resolveCatalogItem, class [mscorlib]System.Collections.Generic.IList`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property> properties, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfoCollection dataSets)
0x44c2  ldstr    aGoal// "Goal"
0x44c7  ldarg.1
0x44c8  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiData [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::get_Data()
0x44cd  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiData::get_Goal()
0x44d2  ldarg.1
0x44d3  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiValues [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::get_Values()
0x44d8  callvirt instance valuetype [mscorlib]System.Nullable`1<float64> [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiValues::get_Goal()
0x44dd  box      valuetype [mscorlib]System.Nullable`1<float64>
0x44e2  ldarg.2
0x44e3  ldloc.0
0x44e4  ldloc.1
0x44e5  call     void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ResolveKpiDataItemProperties(string dataItemName, class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem kpiDataItem, object value, class Microsoft.ReportingServices.Portal.Services.Extensions.ResolveCatalogItem resolveCatalogItem, class [mscorlib]System.Collections.Generic.IList`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property> properties, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfoCollection dataSets)
0x44ea  ldstr    aStatus// "Status"
0x44ef  ldarg.1
0x44f0  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiData [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::get_Data()
0x44f5  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiData::get_Status()
0x44fa  ldarg.1
0x44fb  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiValues [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::get_Values()
0x4500  callvirt instance valuetype [mscorlib]System.Nullable`1<float64> [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiValues::get_Status()
0x4505  box      valuetype [mscorlib]System.Nullable`1<float64>
0x450a  ldarg.2
0x450b  ldloc.0
0x450c  ldloc.1
0x450d  call     void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ResolveKpiDataItemProperties(string dataItemName, class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem kpiDataItem, object value, class Microsoft.ReportingServices.Portal.Services.Extensions.ResolveCatalogItem resolveCatalogItem, class [mscorlib]System.Collections.Generic.IList`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property> properties, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfoCollection dataSets)
0x4512  ldstr    aTrendset// "TrendSet"
0x4517  ldarg.1
0x4518  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiData [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::get_Data()
0x451d  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiData::get_TrendSet()
0x4522  ldarg.1
0x4523  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiValues [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::get_Values()
0x4528  callvirt instance valuetype [mscorlib]System.Nullable`1<float64>[] [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiValues::get_TrendSet()
0x452d  ldarg.2
0x452e  ldloc.0
0x452f  ldloc.1
0x4530  call     void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ResolveKpiDataItemProperties(string dataItemName, class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem kpiDataItem, object value, class Microsoft.ReportingServices.Portal.Services.Extensions.ResolveCatalogItem resolveCatalogItem, class [mscorlib]System.Collections.Generic.IList`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property> properties, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfoCollection dataSets)
0x4535  ldarg.s  4
0x4537  ldloc.1
0x4538  stind.ref
0x4539  ldarg.3
0x453a  ldloc.0
0x453b  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::ToArray()
0x4540  stind.ref
0x4541  ret
```
