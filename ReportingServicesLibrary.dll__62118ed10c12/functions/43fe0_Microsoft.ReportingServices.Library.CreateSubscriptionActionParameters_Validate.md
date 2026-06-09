# Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::Validate

- ea: `0x43fe0`
- end: `0x440d1`
- name: `Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::Validate`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x43cb0`
- `0x43ce0`
- `0x43d00`
- `0x43d20`
- `0x43d60`
- `0x43dc0`
- `0x43fe0`
- `0x70780`
- `0x732b0`

## string_xrefs

- `0x43ffb`: `ItemPath`
- `0x4400e`: `ExtensionSettings`
- `0x440b6`: `ExtensionSettings`
- `0x44043`: `SnapshotUpdated`

## pseudocode

```c

```

## disassembly

```asm
0x43fe0  ldarg.0
0x43fe1  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_Report()
0x43fe6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x43feb  brfalse.s loc_44006
0x43fed  call     bool Microsoft.ReportingServices.Library.Soap.CallingEndpoint::get_Is2010Endpoint()
0x43ff2  brtrue.s loc_43FFB
0x43ff4  ldstr    aReport_1// "Report"
0x43ff9  br.s     loc_44000
0x43ffb  ldstr    aItempath// "ItemPath"
0x44000  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x44005  throw
0x44006  ldarg.0
0x44007  call     instance class Microsoft.ReportingServices.Library.Soap.ExtensionSettings Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_ExtensionSettings()
0x4400c  brtrue.s loc_44019
0x4400e  ldstr    aExtensionsetti_0// "ExtensionSettings"
0x44013  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x44018  throw
0x44019  ldarg.0
0x4401a  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_EventType()
0x4401f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x44024  brfalse.s loc_44031
0x44026  ldstr    aEventtype// "EventType"
0x4402b  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x44030  throw
0x44031  ldstr    aTimedsubscript// "TimedSubscription"
0x44036  ldarg.0
0x44037  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_EventType()
0x4403c  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x44041  brfalse.s loc_44060
0x44043  ldstr    aSnapshotupdate// "SnapshotUpdated"
0x44048  ldarg.0
0x44049  call     instance string Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_EventType()
0x4404e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x44053  brfalse.s loc_44060
0x44055  ldstr    aEventtype// "EventType"
0x4405a  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException::.ctor(string)
0x4405f  throw
0x44060  ldarg.0
0x44061  call     instance bool Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_IsDataDriven()
0x44066  brfalse.s loc_440AB
0x44068  ldarg.0
0x44069  call     instance class Microsoft.ReportingServices.Library.Soap2005.DataRetrievalPlan Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_DataSettings()
0x4406e  brtrue.s loc_4407B
0x44070  ldstr    aDataretrievalp// "DataRetrievalPlan"
0x44075  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x4407a  throw
0x4407b  ldarg.0
0x4407c  call     instance class Microsoft.ReportingServices.Library.Soap2005.DataRetrievalPlan Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_DataSettings()
0x44081  ldfld    class Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinitionOrReference Microsoft.ReportingServices.Library.Soap2005.DataRetrievalPlan::Item
0x44086  brtrue.s loc_44093
0x44088  ldstr    aDatasourcedefi_0// "DataSourceDefinitionOrReference"
0x4408d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x44092  throw
0x44093  ldarg.0
0x44094  call     instance class Microsoft.ReportingServices.Library.Soap2005.DataRetrievalPlan Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_DataSettings()
0x44099  ldfld    class Microsoft.ReportingServices.Library.Soap.DataSetDefinition Microsoft.ReportingServices.Library.Soap2005.DataRetrievalPlan::DataSet
0x4409e  brtrue.s loc_440AB
0x440a0  ldstr    aDatasetdefinit// "DataSetDefinition"
0x440a5  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x440aa  throw
0x440ab  ldarg.0
0x440ac  call     instance class Microsoft.ReportingServices.Library.Soap.ExtensionSettings Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_ExtensionSettings()
0x440b1  ldfld    class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.Soap.ExtensionSettings::ParameterValues
0x440b6  ldstr    aExtensionsetti_0// "ExtensionSettings"
0x440bb  call     void Microsoft.ReportingServices.Library.Soap.Subscription::CheckParameterArray(class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] parameters, string parameterName)
0x440c0  ldarg.0
0x440c1  call     instance class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.CreateSubscriptionActionParameters::get_Parameters()
0x440c6  ldstr    aParameters_0// "Parameters"
0x440cb  call     void Microsoft.ReportingServices.Library.Soap.Subscription::CheckParameterArray(class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] parameters, string parameterName)
0x440d0  ret
```
