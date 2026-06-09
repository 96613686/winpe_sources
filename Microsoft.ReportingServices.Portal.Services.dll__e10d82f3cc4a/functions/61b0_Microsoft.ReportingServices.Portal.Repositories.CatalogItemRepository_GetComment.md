# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetComment

- ea: `0x61b0`
- end: `0x61e3`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetComment`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x6240`
- `0x6530`

## callees

- `0x61b0`
- `0x65f0`
- `0x9e80`
- `0xd780`

## pseudocode

```c

```

## disassembly

```asm
0x61b0  ldarg.0
0x61b1  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_catalogAccessor
0x61b6  ldarg.2
0x61b7  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.CommentEntity> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor::GetCommentAsync(int64)
0x61bc  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.CommentEntity>::get_Result()
0x61c1  stloc.0
0x61c2  ldloc.0
0x61c3  brtrue.s loc_61C7
0x61c5  ldnull
0x61c6  ret
0x61c7  ldarg.1
0x61c8  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x61cd  stloc.1
0x61ce  ldarg.0
0x61cf  ldloc.1
0x61d0  ldloc.0
0x61d1  callvirt instance string [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.CommentEntity::get_ItemPath()
0x61d6  ldc.i4.0
0x61d7  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CheckCommentPermissions(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string path, bool checkDelete)
0x61dc  ldloc.0
0x61dd  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment Microsoft.ReportingServices.Portal.Services.ODataExtensions.CommentExtensions::ToOdataModel(class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.CommentEntity comment)
0x61e2  ret
```
