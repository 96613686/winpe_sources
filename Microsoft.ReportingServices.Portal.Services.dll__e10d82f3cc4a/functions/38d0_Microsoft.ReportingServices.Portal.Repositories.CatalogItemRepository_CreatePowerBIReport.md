# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreatePowerBIReport

- ea: `0x38d0`
- end: `0x3afd`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreatePowerBIReport`
- size: `557`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x2530`
- `0x3830`

## callees

- `0x2370`
- `0x38d0`
- `0x3be0`
- `0x6940`
- `0x6f30`

## string_xrefs

- `0x38e0`: `CreatePowerBIReport`

## pseudocode

```c

```

## disassembly

```asm
0x38d0  ldc.i4.3
0x38d1  newarr   [mscorlib]System.String
0x38d6  dup
0x38d7  ldc.i4.0
0x38d8  ldstr    aSql// "SQL"
0x38dd  stelem.ref
0x38de  dup
0x38df  ldc.i4.1
0x38e0  ldstr    aCreatepowerbir// "CreatePowerBIReport"
0x38e5  stelem.ref
0x38e6  dup
0x38e7  ldc.i4.2
0x38e8  ldarg.s  5
0x38ea  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x38ef  stelem.ref
0x38f0  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0x38f5  stloc.0
0x38f6  ldarg.s  5
0x38f8  ldarg.s  5
0x38fa  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x38ff  callvirt instance string [mscorlib]System.String::Trim()
0x3904  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Name(string)
0x3909  ldarg.s  5
0x390b  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x3910  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x3915  ldstr    aPbix_0// ".PBIX"
0x391a  ldc.i4.5
0x391b  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3920  brfalse.s loc_3935
0x3922  ldarg.s  5
0x3924  ldarg.s  5
0x3926  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x392b  call     string [mscorlib]System.IO.Path::GetFileNameWithoutExtension(string)
0x3930  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Name(string)
0x3935  ldarg.s  5
0x3937  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x393c  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x3941  ldstr    aPbix_0// ".PBIX"
0x3946  ldc.i4.5
0x3947  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x394c  brfalse.s loc_3988
0x394e  ldarg.s  5
0x3950  ldarg.3
0x3951  ldstr    asc_25576// "/"
0x3956  ldc.i4.5
0x3957  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x395c  brtrue.s loc_3972
0x395e  ldstr    a01// "{0}/{1}"
0x3963  ldarg.3
0x3964  ldarg.s  5
0x3966  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x396b  call     string [mscorlib]System.String::Format(string, object, object)
0x3970  br.s     loc_3983
0x3972  ldstr    a0// "/{0}"
0x3977  ldarg.s  5
0x3979  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x397e  call     string [mscorlib]System.String::Format(string, object)
0x3983  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Path(string)
0x3988  ldarg.1
0x3989  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UploadPowerBIReportAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_UploadPowerBiReportAction()
0x398e  dup
0x398f  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UploadPowerBIReportActionParameters>::get_ActionParameters()
0x3994  stloc.1
0x3995  ldloc.1
0x3996  ldarg.s  5
0x3998  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x399d  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_ItemName(string)
0x39a2  ldloc.1
0x39a3  ldarg.3
0x39a4  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_ParentPath(string)
0x39a9  ldloc.1
0x39aa  ldarg.s  4
0x39ac  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_Overwrite(bool)
0x39b1  ldarg.s  5
0x39b3  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter> [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::get_DataModelParameters()
0x39b8  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0x39bd  stloc.2
0x39be  ldloc.1
0x39bf  ldarg.s  5
0x39c1  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::GetOriginalPbiStream()
0x39c6  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UploadPowerBIReportActionParameters::set_Original(class [mscorlib]System.IO.Stream)
0x39cb  ldloc.1
0x39cc  ldarg.s  5
0x39ce  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::GetPbixStream()
0x39d3  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UploadPowerBIReportActionParameters::set_Pbix(class [mscorlib]System.IO.Stream)
0x39d8  ldloc.1
0x39d9  ldarg.s  5
0x39db  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::GetModelStream()
0x39e0  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UploadPowerBIReportActionParameters::set_Model(class [mscorlib]System.IO.Stream)
0x39e5  ldloc.1
0x39e6  ldloc.2
0x39e7  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UploadPowerBIReportActionParameters::set_DataModelParameters(string)
0x39ec  ldarg.s  6
0x39ee  brfalse.s loc_3A2A
0x39f0  ldarg.s  6
0x39f2  call     T0x2B000018
0x39f7  brfalse.s loc_3A2A
0x39f9  ldloc.1
0x39fa  ldarg.s  6
0x39fc  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property> <>c::<>9__81_0
0x3a01  dup
0x3a02  brtrue.s loc_3A1B
0x3a04  pop
0x3a05  ldsfld   class <>c <>c::<>9
0x3a0a  ldftn    instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property <>c::<CreatePowerBIReport>b__81_0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property prop)
0x3a10  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::.ctor(object, native int)
0x3a15  dup
0x3a16  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property> <>c::<>9__81_0
0x3a1b  call     T0x2B000019
0x3a20  call     T0x2B00001A
0x3a25  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_Properties(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[])
0x3a2a  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.UploadPowerBIReportActionParameters>::Execute()
0x3a2f  ldarg.s  5
0x3a31  ldloc.1
0x3a32  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::get_ItemInfo()
0x3a37  callvirt instance valuetype [mscorlib]System.Guid [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::get_ItemID()
0x3a3c  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Id(valuetype [mscorlib]System.Guid)
0x3a41  ldarg.0
0x3a42  ldarg.2
0x3a43  ldloc.1
0x3a44  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::get_ItemInfo()
0x3a49  callvirt instance valuetype [mscorlib]System.Guid [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::get_ItemID()
0x3a4e  ldarg.s  5
0x3a50  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::get_DataSources()
0x3a55  ldarg.s  4
0x3a57  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SetDataModelDataSourcesTrusted(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, valuetype [mscorlib]System.Guid itemId, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> dataSources, bool isOverwrite)
0x3a5c  ldarg.0
0x3a5d  ldloc.1
0x3a5e  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::get_ItemInfo()
0x3a63  callvirt instance valuetype [mscorlib]System.Guid [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::get_ItemID()
0x3a68  ldarg.s  5
0x3a6a  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole> [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::get_DataModelRoles()
0x3a6f  ldarg.s  4
0x3a71  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SetDataModelRolesTrusted(valuetype [mscorlib]System.Guid itemId, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole> dataModelRoles, bool isOverwrite)
0x3a76  ldarg.0
0x3a77  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelDataSourceAccessor
0x3a7c  ldarg.s  5
0x3a7e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0x3a83  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelDataSourceAccessor::GetDataModelDataSourcesByItemAsync(valuetype [mscorlib]System.Guid)
0x3a88  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity>>::get_Result()
0x3a8d  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <>c::<>9__81_1
0x3a92  dup
0x3a93  brtrue.s loc_3AAC
0x3a95  pop
0x3a96  ldsfld   class <>c <>c::<>9
0x3a9b  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource <>c::<CreatePowerBIReport>b__81_1(class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity x)
0x3aa1  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::.ctor(object, native int)
0x3aa6  dup
0x3aa7  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelDataSourceEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> <>c::<>9__81_1
0x3aac  call     T0x2B000001
0x3ab1  stloc.3
0x3ab2  ldarg.0
0x3ab3  ldloc.3
0x3ab4  call     instance bool Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::IsModelRefreshAllowed(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> updatedDataModelDatasources)
0x3ab9  stloc.s  4
0x3abb  ldarg.0
0x3abc  ldarg.2
0x3abd  ldarg.s  5
0x3abf  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x3ac4  ldc.i4.1
0x3ac5  newarr   [Microsoft.ReportingServices.Portal.Interfaces]Model.Property
0x3aca  dup
0x3acb  ldc.i4.0
0x3acc  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::.ctor()
0x3ad1  dup
0x3ad2  ldstr    aModelrefreshal// "ModelRefreshAllowed"
0x3ad7  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::set_Name(string)
0x3adc  dup
0x3add  ldloca.s 4
0x3adf  call     instance string [mscorlib]System.Boolean::ToString()
0x3ae4  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::set_Value(string)
0x3ae9  stelem.ref
0x3aea  ldc.i4.1
0x3aeb  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SetItemPropertiesInternal(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> properties, bool ignoreSecurityCheck)
0x3af0  leave.s  loc_3AFC
0x3af2  ldloc.0
0x3af3  brfalse.s loc_3AFB
0x3af5  ldloc.0
0x3af6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3afb  endfinally
0x3afc  ret
```
