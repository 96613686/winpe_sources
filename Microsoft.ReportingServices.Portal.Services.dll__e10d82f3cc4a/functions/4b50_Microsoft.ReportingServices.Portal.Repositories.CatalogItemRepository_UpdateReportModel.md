# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateReportModel

- ea: `0x4b50`
- end: `0x4c74`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateReportModel`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2a20`

## callees

- `0x4b50`
- `0x4c80`
- `0x9e80`
- `0x128c0`
- `0x1def0`

## pseudocode

```c

```

## disassembly

```asm
0x4b50  newobj   instance void <>c__DisplayClass104_0::.ctor()
0x4b55  stloc.0
0x4b56  ldloc.0
0x4b57  ldarg.s  4
0x4b59  stfld    bool <>c__DisplayClass104_0::renameOrMove
0x4b5e  ldloc.0
0x4b5f  ldarg.0
0x4b60  stfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass104_0::<>4__this
0x4b65  ldloc.0
0x4b66  ldarg.2
0x4b67  stfld    string <>c__DisplayClass104_0::origItemPath
0x4b6c  ldloc.0
0x4b6d  ldarg.3
0x4b6e  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportModel <>c__DisplayClass104_0::reportModel
0x4b73  ldc.i4.1
0x4b74  stloc.1
0x4b75  ldc.i4.1
0x4b76  stloc.2
0x4b77  ldloc.0
0x4b78  ldarg.1
0x4b79  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x4b7e  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass104_0::rsService
0x4b83  ldarg.s  5
0x4b85  brfalse.s loc_4B94
0x4b87  ldarg.0
0x4b88  ldarg.s  5
0x4b8a  ldnull
0x4b8b  ldloca.s 2
0x4b8d  ldloca.s 1
0x4b8f  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ValidateUpdateForFields(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> updatedFields, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource datasource, [out] bool& containsPasswordSensitiveFields, [out] bool& containsHiddenOrDescription)
0x4b94  ldloc.0
0x4b95  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportModel <>c__DisplayClass104_0::reportModel
0x4b9a  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x4b9f  ldc.i4.6
0x4ba0  ldstr    aName// "Name"
0x4ba5  call     void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Global::CheckItemName(string, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType, string)
0x4baa  ldloc.1
0x4bab  brfalse  loc_4C44
0x4bb0  ldloc.0
0x4bb1  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass104_0::rsService
0x4bb6  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_SetPropertiesAction()
0x4bbb  stloc.3
0x4bbc  ldloc.3
0x4bbd  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters>::get_ActionParameters()
0x4bc2  ldloc.0
0x4bc3  ldfld    string <>c__DisplayClass104_0::origItemPath
0x4bc8  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters::set_ItemPath(string)
0x4bcd  ldloc.3
0x4bce  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters>::get_ActionParameters()
0x4bd3  ldc.i4.2
0x4bd4  newarr   [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property
0x4bd9  dup
0x4bda  ldc.i4.0
0x4bdb  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x4be0  dup
0x4be1  ldstr    aHidden// "Hidden"
0x4be6  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x4beb  dup
0x4bec  ldloc.0
0x4bed  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportModel <>c__DisplayClass104_0::reportModel
0x4bf2  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Hidden()
0x4bf7  brtrue.s loc_4C05
0x4bf9  ldc.i4.0
0x4bfa  stloc.s  4
0x4bfc  ldloca.s 4
0x4bfe  call     instance string [mscorlib]System.Boolean::ToString()
0x4c03  br.s     loc_4C0F
0x4c05  ldc.i4.1
0x4c06  stloc.s  4
0x4c08  ldloca.s 4
0x4c0a  call     instance string [mscorlib]System.Boolean::ToString()
0x4c0f  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x4c14  stelem.ref
0x4c15  dup
0x4c16  ldc.i4.1
0x4c17  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x4c1c  dup
0x4c1d  ldstr    aDescription// "Description"
0x4c22  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x4c27  dup
0x4c28  ldloc.0
0x4c29  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportModel <>c__DisplayClass104_0::reportModel
0x4c2e  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Description()
0x4c33  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x4c38  stelem.ref
0x4c39  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters::set_Properties(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[])
0x4c3e  ldloc.3
0x4c3f  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters>::Execute()
0x4c44  ldloc.0
0x4c45  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass104_0::rsService
0x4c4a  ldloc.0
0x4c4b  ldftn    instance void <>c__DisplayClass104_0::<UpdateReportModel>b__0()
0x4c51  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x4c56  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action)
0x4c5b  ldarg.0
0x4c5c  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x4c61  ldc.i4.3
0x4c62  ldloc.0
0x4c63  ldftn    instance string <>c__DisplayClass104_0::<UpdateReportModel>b__1()
0x4c69  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x4c6e  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0x4c73  ret
```
