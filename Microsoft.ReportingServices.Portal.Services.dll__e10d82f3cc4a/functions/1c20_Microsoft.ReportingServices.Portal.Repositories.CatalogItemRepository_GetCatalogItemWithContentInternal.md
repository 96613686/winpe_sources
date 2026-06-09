# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItemWithContentInternal

- ea: `0x1c20`
- end: `0x1e0b`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItemWithContentInternal`
- size: `491`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1be0`
- `0x1c00`
- `0x1e40`
- `0x1e60`

## callees

- `0x1a90`
- `0x1c20`
- `0x128c0`
- `0x128e0`
- `0x1cf90`

## pseudocode

```c

```

## disassembly

```asm
0x1c20  newobj   instance void <>c__DisplayClass25_0::.ctor()
0x1c25  stloc.0
0x1c26  ldloc.0
0x1c27  ldarg.2
0x1c28  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass25_0::rsService
0x1c2d  ldloc.0
0x1c2e  ldarg.3
0x1c2f  stfld    string <>c__DisplayClass25_0::path
0x1c34  ldloc.0
0x1c35  ldarg.s  4
0x1c37  stfld    bool <>c__DisplayClass25_0::internalUse
0x1c3c  ldloc.0
0x1c3d  ldarg.0
0x1c3e  stfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass25_0::<>4__this
0x1c43  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1c48  pop
0x1c49  ldloc.0
0x1c4a  ldnull
0x1c4b  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem <>c__DisplayClass25_0::catalogItem
0x1c50  ldloc.0
0x1c51  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass25_0::rsService
0x1c56  ldloc.0
0x1c57  ldftn    instance void <>c__DisplayClass25_0::<GetCatalogItemWithContentInternal>b__0()
0x1c5d  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x1c62  ldc.i4.1
0x1c63  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action, valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType transactionType)
0x1c68  leave.s  loc_1C81
0x1c6a  stloc.1
0x1c6b  ldloc.1
0x1c6c  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x1c71  brfalse.s loc_1C7F
0x1c73  ldloc.1
0x1c74  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x1c79  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_Code()
0x1c7e  pop
0x1c7f  ldloc.1
0x1c80  throw
0x1c81  ldloc.0
0x1c82  ldarg.0
0x1c83  ldarg.1
0x1c84  ldloc.0
0x1c85  ldfld    string <>c__DisplayClass25_0::path
0x1c8a  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x1c8f  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass25_0::item
0x1c94  ldloc.0
0x1c95  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem <>c__DisplayClass25_0::catalogItem
0x1c9a  callvirt instance unsigned int8[] [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::get_Content()
0x1c9f  brfalse.s loc_1CC7
0x1ca1  ldloc.0
0x1ca2  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem <>c__DisplayClass25_0::catalogItem
0x1ca7  callvirt instance unsigned int8[] [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::get_Content()
0x1cac  ldlen
0x1cad  brfalse.s loc_1CC7
0x1caf  ldloc.0
0x1cb0  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass25_0::item
0x1cb5  ldloc.0
0x1cb6  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem <>c__DisplayClass25_0::catalogItem
0x1cbb  callvirt instance unsigned int8[] [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::get_Content()
0x1cc0  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Content(unsigned int8[])
0x1cc5  br.s     loc_1CE8
0x1cc7  ldloc.0
0x1cc8  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass25_0::item
0x1ccd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0x1cd2  ldc.i4.2
0x1cd3  call     class [mscorlib]System.IO.Stream [Microsoft.ReportingServices.CatalogAccess]Microsoft.ReportingServices.CatalogAccess.Streams.VarbinaryReadableStreamFactory::CreateExtendedContentReadableStream(valuetype [mscorlib]System.Guid, valuetype [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ExtendedContentType)
0x1cd8  stloc.2
0x1cd9  ldloc.2
0x1cda  brfalse.s loc_1CE8
0x1cdc  ldloc.0
0x1cdd  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass25_0::item
0x1ce2  ldloc.2
0x1ce3  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::SetContent(class [mscorlib]System.IO.Stream)
0x1ce8  ldloc.0
0x1ce9  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass25_0::rsService
0x1cee  ldloc.0
0x1cef  ldftn    instance void <>c__DisplayClass25_0::<GetCatalogItemWithContentInternal>b__1()
0x1cf5  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x1cfa  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action)
0x1cff  ldloc.0
0x1d00  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass25_0::rsService
0x1d05  ldloc.0
0x1d06  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass25_0::item
0x1d0b  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x1d10  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::IsTrustedFileType(string)
0x1d15  brfalse.s loc_1D2F
0x1d17  ldloc.0
0x1d18  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass25_0::rsService
0x1d1d  ldloc.0
0x1d1e  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass25_0::item
0x1d23  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_ContentType()
0x1d28  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::IsTrustedContentType(string)
0x1d2d  brtrue.s loc_1D3F
0x1d2f  ldloc.0
0x1d30  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass25_0::item
0x1d35  ldstr    aApplicationOct// "application/octet-stream"
0x1d3a  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_ContentType(string)
0x1d3f  ldloc.0
0x1d40  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass25_0::item
0x1d45  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x1d4a  ldc.i4.6
0x1d4b  bne.un   loc_1E04
0x1d50  ldloc.0
0x1d51  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass25_0::item
0x1d56  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x1d5b  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x1d60  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1d65  brfalse  loc_1E04
0x1d6a  ldloc.0
0x1d6b  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass25_0::rsService
0x1d70  ldloc.0
0x1d71  ldftn    instance void <>c__DisplayClass25_0::<GetCatalogItemWithContentInternal>b__2()
0x1d77  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x1d7c  ldc.i4.1
0x1d7d  call     void Microsoft.ReportingServices.Portal.Services.Extensions.RsServiceExtensions::ExecuteStorageAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Action action, valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType transactionType)
0x1d82  ldloc.0
0x1d83  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem <>c__DisplayClass25_0::catalogItem
0x1d88  isinst   [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ResourceCatalogItem
0x1d8d  stloc.3
0x1d8e  ldloc.0
0x1d8f  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass25_0::item
0x1d94  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x1d99  ldstr    aFbac82c89bad4d// "fbac82c8-9bad-4dba-929f-c04e7ca4111f/lo"...
0x1d9e  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x1da3  brfalse.s loc_1DB8
0x1da5  ldloc.0
0x1da6  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass25_0::item
0x1dab  ldloc.3
0x1dac  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ResourceCatalogItem::get_MimeType()
0x1db1  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_ContentType(string)
0x1db6  br.s     loc_1DE7
0x1db8  ldloc.0
0x1db9  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem <>c__DisplayClass25_0::catalogItem
0x1dbe  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemProperties [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::get_Properties()
0x1dc3  brfalse.s loc_1DE7
0x1dc5  ldloc.0
0x1dc6  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem <>c__DisplayClass25_0::catalogItem
0x1dcb  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemProperties [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::get_Properties()
0x1dd0  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemProperties::get_SubType()
0x1dd5  brfalse.s loc_1DE7
0x1dd7  ldloc.0
0x1dd8  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass25_0::item
0x1ddd  ldstr    aImagePng// "image/png"
0x1de2  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_ContentType(string)
0x1de7  leave.s  loc_1E04
0x1de9  stloc.s  4
0x1deb  ldloc.s  4
0x1ded  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x1df2  brfalse.s loc_1E01
0x1df4  ldloc.s  4
0x1df6  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x1dfb  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException::get_Code()
0x1e00  pop
0x1e01  ldloc.s  4
0x1e03  throw
0x1e04  ldloc.0
0x1e05  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass25_0::item
0x1e0a  ret
```
