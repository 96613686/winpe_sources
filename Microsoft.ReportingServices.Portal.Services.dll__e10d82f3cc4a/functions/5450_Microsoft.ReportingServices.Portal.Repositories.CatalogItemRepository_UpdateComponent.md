# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateComponent

- ea: `0x5450`
- end: `0x54f1`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateComponent`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2a20`

## callees

- `0x5450`
- `0x5500`
- `0x9e80`
- `0x128c0`
- `0x1e1a0`

## pseudocode

```c

```

## disassembly

```asm
0x5450  newobj   instance void <>c__DisplayClass122_0::.ctor()
0x5455  stloc.0
0x5456  ldloc.0
0x5457  ldarg.0
0x5458  stfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass122_0::<>4__this
0x545d  ldloc.0
0x545e  ldarg.3
0x545f  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Component <>c__DisplayClass122_0::item
0x5464  ldloc.0
0x5465  ldarg.2
0x5466  stfld    string <>c__DisplayClass122_0::origItemPath
0x546b  ldloc.0
0x546c  ldarg.s  4
0x546e  stfld    bool <>c__DisplayClass122_0::renameOrMove
0x5473  ldc.i4.2
0x5474  newarr   [mscorlib]System.String
0x5479  dup
0x547a  ldc.i4.0
0x547b  ldstr    aHidden// "Hidden"
0x5480  stelem.ref
0x5481  dup
0x5482  ldc.i4.1
0x5483  ldstr    aDescription// "Description"
0x5488  stelem.ref
0x5489  stloc.1
0x548a  ldloc.0
0x548b  ldc.i4.1
0x548c  stfld    bool <>c__DisplayClass122_0::updateProperties
0x5491  ldloc.0
0x5492  ldarg.1
0x5493  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x5498  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass122_0::rsService
0x549d  ldarg.s  5
0x549f  brfalse.s loc_54B7
0x54a1  ldloc.0
0x54a2  ldarg.s  5
0x54a4  ldloc.1
0x54a5  call     T0x2B00002C
0x54aa  call     T0x2B00002D
0x54af  ldc.i4.0
0x54b0  cgt
0x54b2  stfld    bool <>c__DisplayClass122_0::updateProperties
0x54b7  ldloc.0
0x54b8  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Component <>c__DisplayClass122_0::item
0x54bd  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0x54c2  ldlen
0x54c3  brfalse.s loc_54D9
0x54c5  ldarg.0
0x54c6  ldarg.1
0x54c7  ldloc.0
0x54c8  ldfld    string <>c__DisplayClass122_0::origItemPath
0x54cd  ldloc.0
0x54ce  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.Component <>c__DisplayClass122_0::item
0x54d3  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ReplaceComponentContent(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string originalPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Component item)
0x54d8  ret
0x54d9  ldloc.0
0x54da  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass122_0::rsService
0x54df  ldloc.0
0x54e0  ldftn    instance void <>c__DisplayClass122_0::<UpdateComponent>b__0()
0x54e6  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x54eb  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action)
0x54f0  ret
```
