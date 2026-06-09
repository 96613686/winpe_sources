# Microsoft.ReportingServices.Library.CreateCacheRefreshPlanActionParameters::Validate

- ea: `0x45820`
- end: `0x458bd`
- name: `Microsoft.ReportingServices.Library.CreateCacheRefreshPlanActionParameters::Validate`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x45620`
- `0x45640`
- `0x45690`
- `0x45700`
- `0x45820`
- `0x6dc30`
- `0x732b0`

## string_xrefs

- `0x45850`: `ItemPath`
- `0x45873`: `RefreshCache`

## pseudocode

```c

```

## disassembly

```asm
0x45820  ldarg.0
0x45821  call     instance valuetype Microsoft.ReportingServices.Library.ItemType Microsoft.ReportingServices.Library.CreateCacheRefreshPlanActionParameters::get_ItemType()
0x45826  ldc.i4.s 0xD
0x45828  beq.s    loc_45843
0x4582a  ldarg.0
0x4582b  call     instance valuetype Microsoft.ReportingServices.Library.ItemType Microsoft.ReportingServices.Library.CreateCacheRefreshPlanActionParameters::get_ItemType()
0x45830  call     valuetype Microsoft.ReportingServices.Library.Soap2010.ItemTypeEnum Microsoft.ReportingServices.Library.Soap2010.CatalogItem::ItemTypeToSoapType(valuetype Microsoft.ReportingServices.Library.ItemType type)
0x45835  brtrue.s loc_45843
0x45837  ldarg.0
0x45838  call     instance string Microsoft.ReportingServices.Library.CreateCacheRefreshPlanActionParameters::get_ItemPath()
0x4583d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemNotFoundException::.ctor(string)
0x45842  throw
0x45843  ldarg.0
0x45844  call     instance string Microsoft.ReportingServices.Library.CreateCacheRefreshPlanActionParameters::get_ItemPath()
0x45849  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4584e  brfalse.s loc_4585B
0x45850  ldstr    aItempath// "ItemPath"
0x45855  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x4585a  throw
0x4585b  ldarg.0
0x4585c  call     instance string Microsoft.ReportingServices.Library.CreateCacheRefreshPlanActionParameters::get_EventType()
0x45861  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x45866  brfalse.s loc_45873
0x45868  ldstr    aEventtype// "EventType"
0x4586d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x45872  throw
0x45873  ldstr    aRefreshcache// "RefreshCache"
0x45878  ldarg.0
0x45879  call     instance string Microsoft.ReportingServices.Library.CreateCacheRefreshPlanActionParameters::get_EventType()
0x4587e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x45883  brfalse.s loc_458AC
0x45885  ldarg.0
0x45886  call     instance string Microsoft.ReportingServices.Library.CreateCacheRefreshPlanActionParameters::get_EventType()
0x4588b  ldstr    aDatamodelrefre// "DataModelRefresh"
0x45890  callvirt instance bool [mscorlib]System.String::Equals(string)
0x45895  brfalse.s loc_458AC
0x45897  ldarg.0
0x45898  call     instance valuetype Microsoft.ReportingServices.Library.ItemType Microsoft.ReportingServices.Library.CreateCacheRefreshPlanActionParameters::get_ItemType()
0x4589d  ldc.i4.s 0xD
0x4589f  beq.s    loc_458AC
0x458a1  ldstr    aEventtype// "EventType"
0x458a6  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException::.ctor(string)
0x458ab  throw
0x458ac  ldarg.0
0x458ad  call     instance class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.CreateCacheRefreshPlanActionParameters::get_Parameters()
0x458b2  ldstr    aParameters_0// "Parameters"
0x458b7  call     void Microsoft.ReportingServices.Library.Soap.Subscription::CheckParameterArray(class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] parameters, string parameterName)
0x458bc  ret
```
