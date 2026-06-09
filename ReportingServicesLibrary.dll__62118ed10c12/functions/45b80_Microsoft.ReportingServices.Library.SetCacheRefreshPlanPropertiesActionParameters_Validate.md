# Microsoft.ReportingServices.Library.SetCacheRefreshPlanPropertiesActionParameters::Validate

- ea: `0x45b80`
- end: `0x45bf0`
- name: `Microsoft.ReportingServices.Library.SetCacheRefreshPlanPropertiesActionParameters::Validate`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x459f0`
- `0x45a40`
- `0x45ab0`
- `0x45b80`
- `0x732b0`

## string_xrefs

- `0x45bb0`: `RefreshCache`
- `0x45b8d`: `CacheRefreshPlanID`

## pseudocode

```c

```

## disassembly

```asm
0x45b80  ldarg.0
0x45b81  call     instance string Microsoft.ReportingServices.Library.SetCacheRefreshPlanPropertiesActionParameters::get_CacheRefreshPlanID()
0x45b86  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x45b8b  brfalse.s loc_45B98
0x45b8d  ldstr    aCacherefreshpl_0// "CacheRefreshPlanID"
0x45b92  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x45b97  throw
0x45b98  ldarg.0
0x45b99  call     instance string Microsoft.ReportingServices.Library.SetCacheRefreshPlanPropertiesActionParameters::get_EventType()
0x45b9e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x45ba3  brfalse.s loc_45BB0
0x45ba5  ldstr    aEventtype// "EventType"
0x45baa  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x45baf  throw
0x45bb0  ldstr    aRefreshcache// "RefreshCache"
0x45bb5  ldarg.0
0x45bb6  call     instance string Microsoft.ReportingServices.Library.SetCacheRefreshPlanPropertiesActionParameters::get_EventType()
0x45bbb  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x45bc0  brfalse.s loc_45BDF
0x45bc2  ldarg.0
0x45bc3  call     instance string Microsoft.ReportingServices.Library.SetCacheRefreshPlanPropertiesActionParameters::get_EventType()
0x45bc8  ldstr    aDatamodelrefre// "DataModelRefresh"
0x45bcd  callvirt instance bool [mscorlib]System.String::Equals(string)
0x45bd2  brtrue.s loc_45BDF
0x45bd4  ldstr    aEventtype// "EventType"
0x45bd9  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException::.ctor(string)
0x45bde  throw
0x45bdf  ldarg.0
0x45be0  call     instance class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.SetCacheRefreshPlanPropertiesActionParameters::get_Parameters()
0x45be5  ldstr    aParameters_0// "Parameters"
0x45bea  call     void Microsoft.ReportingServices.Library.Soap.Subscription::CheckParameterArray(class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] parameters, string parameterName)
0x45bef  ret
```
