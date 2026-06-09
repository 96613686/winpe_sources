# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateDataSource

- ea: `0x49e0`
- end: `0x4b4e`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateDataSource`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2a20`

## callees

- `0x49e0`
- `0x4c80`
- `0x9e80`
- `0x10c80`
- `0x116c0`
- `0x128c0`
- `0x1de80`

## pseudocode

```c

```

## disassembly

```asm
0x49e0  newobj   instance void <>c__DisplayClass103_0::.ctor()
0x49e5  stloc.0
0x49e6  ldloc.0
0x49e7  ldarg.s  4
0x49e9  stfld    bool <>c__DisplayClass103_0::renameOrMove
0x49ee  ldloc.0
0x49ef  ldarg.0
0x49f0  stfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass103_0::<>4__this
0x49f5  ldloc.0
0x49f6  ldarg.2
0x49f7  stfld    string <>c__DisplayClass103_0::origItemPath
0x49fc  ldloc.0
0x49fd  ldarg.3
0x49fe  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c__DisplayClass103_0::dataSource
0x4a03  ldc.i4.1
0x4a04  stloc.1
0x4a05  ldc.i4.1
0x4a06  stloc.2
0x4a07  ldloc.0
0x4a08  ldarg.1
0x4a09  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x4a0e  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass103_0::rsService
0x4a13  ldloc.0
0x4a14  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c__DisplayClass103_0::dataSource
0x4a19  call     void Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions::LoadFromContent(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource dataSource)
0x4a1e  ldarg.s  5
0x4a20  brfalse.s loc_4A34
0x4a22  ldarg.0
0x4a23  ldarg.s  5
0x4a25  ldloc.0
0x4a26  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c__DisplayClass103_0::dataSource
0x4a2b  ldloca.s 2
0x4a2d  ldloca.s 1
0x4a2f  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ValidateUpdateForFields(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> updatedFields, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource datasource, [out] bool& containsPasswordSensitiveFields, [out] bool& containsHiddenOrDescription)
0x4a34  ldloc.0
0x4a35  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c__DisplayClass103_0::dataSource
0x4a3a  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x4a3f  ldc.i4.5
0x4a40  ldstr    aName// "Name"
0x4a45  call     void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Global::CheckItemName(string, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType, string)
0x4a4a  ldloc.2
0x4a4b  brfalse.s loc_4A84
0x4a4d  ldloc.0
0x4a4e  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass103_0::rsService
0x4a53  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetDataSourceContentsAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_SetDataSourceContentsAction()
0x4a58  dup
0x4a59  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetDataSourceContentsActionParameters>::get_ActionParameters()
0x4a5e  ldloc.0
0x4a5f  ldfld    string <>c__DisplayClass103_0::origItemPath
0x4a64  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UpdateItemActionParameters::set_ItemPath(string)
0x4a69  dup
0x4a6a  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetDataSourceContentsActionParameters>::get_ActionParameters()
0x4a6f  ldloc.0
0x4a70  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c__DisplayClass103_0::dataSource
0x4a75  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions::ToDataSourceDefinition(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource dataSource)
0x4a7a  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetDataSourceContentsActionParameters::set_DataSourceDefinition(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition)
0x4a7f  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetDataSourceContentsActionParameters>::Execute()
0x4a84  ldloc.1
0x4a85  brfalse  loc_4B1E
0x4a8a  ldloc.0
0x4a8b  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass103_0::rsService
0x4a90  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_SetPropertiesAction()
0x4a95  stloc.3
0x4a96  ldloc.3
0x4a97  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters>::get_ActionParameters()
0x4a9c  ldloc.0
0x4a9d  ldfld    string <>c__DisplayClass103_0::origItemPath
0x4aa2  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters::set_ItemPath(string)
0x4aa7  ldloc.3
0x4aa8  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters>::get_ActionParameters()
0x4aad  ldc.i4.2
0x4aae  newarr   [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property
0x4ab3  dup
0x4ab4  ldc.i4.0
0x4ab5  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x4aba  dup
0x4abb  ldstr    aHidden// "Hidden"
0x4ac0  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x4ac5  dup
0x4ac6  ldloc.0
0x4ac7  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c__DisplayClass103_0::dataSource
0x4acc  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Hidden()
0x4ad1  brtrue.s loc_4ADF
0x4ad3  ldc.i4.0
0x4ad4  stloc.s  4
0x4ad6  ldloca.s 4
0x4ad8  call     instance string [mscorlib]System.Boolean::ToString()
0x4add  br.s     loc_4AE9
0x4adf  ldc.i4.1
0x4ae0  stloc.s  4
0x4ae2  ldloca.s 4
0x4ae4  call     instance string [mscorlib]System.Boolean::ToString()
0x4ae9  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x4aee  stelem.ref
0x4aef  dup
0x4af0  ldc.i4.1
0x4af1  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x4af6  dup
0x4af7  ldstr    aDescription// "Description"
0x4afc  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x4b01  dup
0x4b02  ldloc.0
0x4b03  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c__DisplayClass103_0::dataSource
0x4b08  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Description()
0x4b0d  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x4b12  stelem.ref
0x4b13  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters::set_Properties(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[])
0x4b18  ldloc.3
0x4b19  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters>::Execute()
0x4b1e  ldloc.0
0x4b1f  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass103_0::rsService
0x4b24  ldloc.0
0x4b25  ldftn    instance void <>c__DisplayClass103_0::<UpdateDataSource>b__0()
0x4b2b  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x4b30  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action)
0x4b35  ldarg.0
0x4b36  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x4b3b  ldc.i4.3
0x4b3c  ldloc.0
0x4b3d  ldftn    instance string <>c__DisplayClass103_0::<UpdateDataSource>b__1()
0x4b43  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x4b48  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0x4b4d  ret
```
