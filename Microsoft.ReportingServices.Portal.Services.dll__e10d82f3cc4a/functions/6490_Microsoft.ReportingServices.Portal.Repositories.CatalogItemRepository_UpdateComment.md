# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateComment

- ea: `0x6490`
- end: `0x6522`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateComment`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x6490`
- `0x65d0`
- `0x9e80`

## string_xrefs

- `0x64c5`: `entity.ItemId is null in UpdateComment`

## pseudocode

```c

```

## disassembly

```asm
0x6490  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Comment::.ctor()
0x6495  dup
0x6496  ldarg.2
0x6497  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_Text()
0x649c  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Comment::set_Text(string)
0x64a1  dup
0x64a2  ldarg.2
0x64a3  callvirt instance int64 [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_Id()
0x64a8  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Comment::set_Id(int64)
0x64ad  stloc.0
0x64ae  ldarg.2
0x64af  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_ItemId()
0x64b4  stloc.2
0x64b5  ldloca.s 2
0x64b7  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x64bc  brtrue.s loc_64CF
0x64be  ldarg.0
0x64bf  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x64c4  ldc.i4.1
0x64c5  ldstr    aEntityItemidIs// "entity.ItemId is null in UpdateComment"
0x64ca  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x64cf  ldarg.1
0x64d0  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x64d5  stloc.1
0x64d6  ldloc.1
0x64d7  ldc.i4.1
0x64d8  call     valuetype [System.Data]System.Data.IsolationLevel [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_DefaultIsolationLevel()
0x64dd  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::SetDatabaseConnectionSettings(valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType, valuetype [System.Data]System.Data.IsolationLevel)
0x64e2  ldarg.0
0x64e3  ldloc.1
0x64e4  ldarg.2
0x64e5  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_ItemId()
0x64ea  stloc.2
0x64eb  ldloca.s 2
0x64ed  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x64f2  ldc.i4.0
0x64f3  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CheckCommentPermissions(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, valuetype [mscorlib]System.Guid itemId, bool checkDelete)
0x64f8  ldloc.1
0x64f9  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSServiceStorageAccess::.ctor(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService)
0x64fe  stloc.3
0x64ff  ldloc.1
0x6500  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IDBInterface [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_Storage()
0x6505  ldloc.0
0x6506  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IDBInterface::UpdateComment(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Comment)
0x650b  ldloc.3
0x650c  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSServiceStorageAccess::Commit()
0x6511  stloc.s  4
0x6513  leave.s  loc_651F
0x6515  ldloc.3
0x6516  brfalse.s loc_651E
0x6518  ldloc.3
0x6519  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x651e  endfinally
0x651f  ldloc.s  4
0x6521  ret
```
