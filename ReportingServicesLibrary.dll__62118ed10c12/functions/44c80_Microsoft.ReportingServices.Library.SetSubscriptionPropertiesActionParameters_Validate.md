# Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::Validate

- ea: `0x44c80`
- end: `0x44dfe`
- name: `Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::Validate`
- size: `382`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x449a0`
- `0x449d0`
- `0x449f0`
- `0x44a10`
- `0x44a50`
- `0x44a80`
- `0x44ab0`
- `0x44c80`
- `0x732b0`

## string_xrefs

- `0x44ce6`: `ExtensionSettings`
- `0x44d7e`: `ExtensionSettings`
- `0x44de3`: `ExtensionSettings`
- `0x44d31`: `SnapshotUpdated`
- `0x44db3`: `SnapshotUpdated`

## pseudocode

```c

```

## disassembly

```asm
0x44c80  ldarg.0
0x44c81  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_SubscriptionID()
0x44c86  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x44c8b  brfalse.s loc_44C98
0x44c8d  ldstr    aSubscriptionid_1// "SubscriptionID"
0x44c92  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x44c97  throw
0x44c98  ldarg.0
0x44c99  call     instance bool Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_IsDataDriven()
0x44c9e  brfalse  loc_44D76
0x44ca3  ldarg.0
0x44ca4  call     instance class Microsoft.ReportingServices.Library.Soap2005.DataRetrievalPlan Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_DataSettings()
0x44ca9  brfalse  loc_44D51
0x44cae  ldarg.0
0x44caf  call     instance class Microsoft.ReportingServices.Library.Soap2005.DataRetrievalPlan Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_DataSettings()
0x44cb4  ldfld    class Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinitionOrReference Microsoft.ReportingServices.Library.Soap2005.DataRetrievalPlan::Item
0x44cb9  brtrue.s loc_44CC6
0x44cbb  ldstr    aDatasourcedefi_0// "DataSourceDefinitionOrReference"
0x44cc0  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x44cc5  throw
0x44cc6  ldarg.0
0x44cc7  call     instance class Microsoft.ReportingServices.Library.Soap2005.DataRetrievalPlan Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_DataSettings()
0x44ccc  ldfld    class Microsoft.ReportingServices.Library.Soap.DataSetDefinition Microsoft.ReportingServices.Library.Soap2005.DataRetrievalPlan::DataSet
0x44cd1  brtrue.s loc_44CDE
0x44cd3  ldstr    aDatasetdefinit// "DataSetDefinition"
0x44cd8  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x44cdd  throw
0x44cde  ldarg.0
0x44cdf  call     instance class Microsoft.ReportingServices.Library.Soap.ExtensionSettings Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_ExtensionSettings()
0x44ce4  brtrue.s loc_44CF1
0x44ce6  ldstr    aExtensionsetti_0// "ExtensionSettings"
0x44ceb  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x44cf0  throw
0x44cf1  ldarg.0
0x44cf2  call     instance class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_Parameters()
0x44cf7  brtrue.s loc_44D04
0x44cf9  ldstr    aParameters_0// "Parameters"
0x44cfe  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x44d03  throw
0x44d04  ldarg.0
0x44d05  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_EventType()
0x44d0a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x44d0f  brfalse.s loc_44D1C
0x44d11  ldstr    aEventtype// "EventType"
0x44d16  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x44d1b  throw
0x44d1c  ldstr    aTimedsubscript// "TimedSubscription"
0x44d21  ldarg.0
0x44d22  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_EventType()
0x44d27  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x44d2c  brfalse  loc_44DD0
0x44d31  ldstr    aSnapshotupdate// "SnapshotUpdated"
0x44d36  ldarg.0
0x44d37  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_EventType()
0x44d3c  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x44d41  brfalse  loc_44DD0
0x44d46  ldstr    aEventtype// "EventType"
0x44d4b  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException::.ctor(string)
0x44d50  throw
0x44d51  ldarg.0
0x44d52  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_MatchData()
0x44d57  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x44d5c  brtrue.s loc_44DD0
0x44d5e  ldarg.0
0x44d5f  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_EventType()
0x44d64  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x44d69  brfalse.s loc_44DD0
0x44d6b  ldstr    aEventtype// "EventType"
0x44d70  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x44d75  throw
0x44d76  ldarg.0
0x44d77  call     instance class Microsoft.ReportingServices.Library.Soap.ExtensionSettings Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_ExtensionSettings()
0x44d7c  brtrue.s loc_44D89
0x44d7e  ldstr    aExtensionsetti_0// "ExtensionSettings"
0x44d83  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x44d88  throw
0x44d89  ldarg.0
0x44d8a  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_EventType()
0x44d8f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x44d94  brfalse.s loc_44DA1
0x44d96  ldstr    aEventtype// "EventType"
0x44d9b  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x44da0  throw
0x44da1  ldstr    aTimedsubscript// "TimedSubscription"
0x44da6  ldarg.0
0x44da7  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_EventType()
0x44dac  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x44db1  brfalse.s loc_44DD0
0x44db3  ldstr    aSnapshotupdate// "SnapshotUpdated"
0x44db8  ldarg.0
0x44db9  call     instance string Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_EventType()
0x44dbe  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x44dc3  brfalse.s loc_44DD0
0x44dc5  ldstr    aEventtype// "EventType"
0x44dca  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException::.ctor(string)
0x44dcf  throw
0x44dd0  ldarg.0
0x44dd1  call     instance class Microsoft.ReportingServices.Library.Soap.ExtensionSettings Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_ExtensionSettings()
0x44dd6  brfalse.s loc_44DED
0x44dd8  ldarg.0
0x44dd9  call     instance class Microsoft.ReportingServices.Library.Soap.ExtensionSettings Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_ExtensionSettings()
0x44dde  ldfld    class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.Soap.ExtensionSettings::ParameterValues
0x44de3  ldstr    aExtensionsetti_0// "ExtensionSettings"
0x44de8  call     void Microsoft.ReportingServices.Library.Soap.Subscription::CheckParameterArray(class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] parameters, string parameterName)
0x44ded  ldarg.0
0x44dee  call     instance class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.SetSubscriptionPropertiesActionParameters::get_Parameters()
0x44df3  ldstr    aParameters_0// "Parameters"
0x44df8  call     void Microsoft.ReportingServices.Library.Soap.Subscription::CheckParameterArray(class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] parameters, string parameterName)
0x44dfd  ret
```
