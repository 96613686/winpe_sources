# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::DeleteComment

- ea: `0x6530`
- end: `0x6598`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::DeleteComment`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x61b0`
- `0x6530`
- `0x65d0`
- `0x9e80`

## string_xrefs

- `0x6550`: `ItemId was null on comment retrieved from the database`

## pseudocode

```c

```

## disassembly

```asm
0x6530  ldarg.0
0x6531  ldarg.1
0x6532  ldarg.2
0x6533  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetComment(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, int64 id)
0x6538  stloc.0
0x6539  ldloc.0
0x653a  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_ItemId()
0x653f  stloc.2
0x6540  ldloca.s 2
0x6542  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x6547  brtrue.s loc_655A
0x6549  ldarg.0
0x654a  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x654f  ldc.i4.1
0x6550  ldstr    aItemidWasNullO// "ItemId was null on comment retrieved fr"...
0x6555  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x655a  ldarg.1
0x655b  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x6560  stloc.1
0x6561  ldloc.1
0x6562  ldc.i4.1
0x6563  call     valuetype [System.Data]System.Data.IsolationLevel [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_DefaultIsolationLevel()
0x6568  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::SetDatabaseConnectionSettings(valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType, valuetype [System.Data]System.Data.IsolationLevel)
0x656d  ldarg.0
0x656e  ldloc.1
0x656f  ldloc.0
0x6570  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_ItemId()
0x6575  stloc.2
0x6576  ldloca.s 2
0x6578  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x657d  ldarg.3
0x657e  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CheckCommentPermissions(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, valuetype [mscorlib]System.Guid itemId, bool checkDelete)
0x6583  ldarg.0
0x6584  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_catalogAccessor
0x6589  ldarg.2
0x658a  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor::DeleteCommentAsync(int64)
0x658f  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<int32>::get_Result()
0x6594  ldc.i4.0
0x6595  cgt
0x6597  ret
```
