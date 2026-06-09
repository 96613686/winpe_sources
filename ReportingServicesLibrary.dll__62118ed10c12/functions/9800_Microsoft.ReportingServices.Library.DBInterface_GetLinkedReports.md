# Microsoft.ReportingServices.Library.DBInterface::GetLinkedReports

- ea: `0x9800`
- end: `0x98c7`
- name: `Microsoft.ReportingServices.Library.DBInterface::GetLinkedReports`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x9800`
- `0x98d0`
- `0x1e270`
- `0x23400`

## string_xrefs

- `0x9813`: `@Link`
- `0x9801`: `GetIDPairsByLink`

## pseudocode

```c

```

## disassembly

```asm
0x9800  ldarg.0
0x9801  ldstr    aGetidpairsbyli// "GetIDPairsByLink"
0x9806  ldnull
0x9807  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x980c  stloc.0
0x980d  ldloc.0
0x980e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x9813  ldstr    aLink_0// "@Link"
0x9818  ldarg.2
0x9819  box      [mscorlib]System.Guid
0x981e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x9823  pop
0x9824  ldarg.0
0x9825  ldloc.0
0x9826  call     instance class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.Library.LinkInfo> Microsoft.ReportingServices.Library.DBInterface::GetIdPairs(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand command)
0x982b  stloc.1
0x982c  ldloc.1
0x982d  brfalse.s loc_9837
0x982f  ldloc.1
0x9830  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.Library.LinkInfo>::get_Count()
0x9835  brtrue.s loc_983F
0x9837  ldnull
0x9838  stloc.s  4
0x983a  leave    loc_98C4
0x983f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.LinkedReportCatalogItem>::.ctor()
0x9844  stloc.2
0x9845  ldloc.1
0x9846  ldc.i4.0
0x9847  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.Library.LinkInfo>::get_Item(!!T0)
0x984c  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.LinkInfo::ReportID
0x9851  stloc.3
0x9852  ldloc.1
0x9853  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.ReportingServices.Library.LinkInfo>::GetEnumerator()
0x9858  stloc.s  5
0x985a  br.s     loc_989C
0x985c  ldloca.s 5
0x985e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype Microsoft.ReportingServices.Library.LinkInfo>::get_Current()
0x9863  stloc.s  6
0x9865  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x986a  ldloc.3
0x986b  ldloc.s  6
0x986d  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.LinkInfo::ReportID
0x9872  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x9877  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0x987c  ldloc.2
0x987d  ldarg.1
0x987e  callvirt instance class Microsoft.ReportingServices.Library.CatalogItemFactory Microsoft.ReportingServices.Library.RSService::get_CatalogItemFactory()
0x9883  ldnull
0x9884  ldloc.s  6
0x9886  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.LinkInfo::LinkID
0x988b  ldc.i4.4
0x988c  ldnull
0x988d  callvirt instance class Microsoft.ReportingServices.Library.CatalogItem Microsoft.ReportingServices.Library.CatalogItemFactory::GetCatalogItem(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext itemContext, valuetype [mscorlib]System.Guid itemID, valuetype Microsoft.ReportingServices.Library.ItemType itemType, unsigned int8[] secDesc)
0x9892  castclass Microsoft.ReportingServices.Library.LinkedReportCatalogItem
0x9897  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.LinkedReportCatalogItem>::Add(var<u1>)
0x989c  ldloca.s 5
0x989e  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype Microsoft.ReportingServices.Library.LinkInfo>::MoveNext()
0x98a3  brtrue.s loc_985C
0x98a5  leave.s  loc_98B5
0x98a7  ldloca.s 5
0x98a9  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype Microsoft.ReportingServices.Library.LinkInfo>
0x98af  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x98b4  endfinally
0x98b5  ldloc.2
0x98b6  stloc.s  4
0x98b8  leave.s  loc_98C4
0x98ba  ldloc.0
0x98bb  brfalse.s loc_98C3
0x98bd  ldloc.0
0x98be  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x98c3  endfinally
0x98c4  ldloc.s  4
0x98c6  ret
```
