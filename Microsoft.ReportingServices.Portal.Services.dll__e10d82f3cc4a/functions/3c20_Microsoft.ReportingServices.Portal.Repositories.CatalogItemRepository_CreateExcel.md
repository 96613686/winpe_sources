# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateExcel

- ea: `0x3c20`
- end: `0x3d9c`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateExcel`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x2530`

## callees

- `0x1ab0`
- `0x2240`
- `0x3c20`
- `0xa830`
- `0x108c0`
- `0x1d9e0`

## string_xrefs

- `0x3c30`: `CreateExcel`

## pseudocode

```c

```

## disassembly

```asm
0x3c20  ldc.i4.2
0x3c21  newarr   [mscorlib]System.String
0x3c26  dup
0x3c27  ldc.i4.0
0x3c28  ldstr    aSql// "SQL"
0x3c2d  stelem.ref
0x3c2e  dup
0x3c2f  ldc.i4.1
0x3c30  ldstr    aCreateexcel// "CreateExcel"
0x3c35  stelem.ref
0x3c36  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0x3c3b  stloc.0
0x3c3c  newobj   instance void <>c__DisplayClass85_0::.ctor()
0x3c41  stloc.1
0x3c42  ldarg.s  5
0x3c44  ldarg.s  5
0x3c46  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x3c4b  callvirt instance string [mscorlib]System.String::Trim()
0x3c50  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Name(string)
0x3c55  ldloc.1
0x3c56  ldarg.s  5
0x3c58  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x3c5d  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x3c62  stfld    string <>c__DisplayClass85_0::fileExtension
0x3c67  ldc.i4.5
0x3c68  newarr   [mscorlib]System.String
0x3c6d  dup
0x3c6e  ldc.i4.0
0x3c6f  ldstr    aXlsx// ".xlsx"
0x3c74  stelem.ref
0x3c75  dup
0x3c76  ldc.i4.1
0x3c77  ldstr    aXlsb// ".xlsb"
0x3c7c  stelem.ref
0x3c7d  dup
0x3c7e  ldc.i4.2
0x3c7f  ldstr    aXls// ".xls"
0x3c84  stelem.ref
0x3c85  dup
0x3c86  ldc.i4.3
0x3c87  ldstr    aXlsm// ".xlsm"
0x3c8c  stelem.ref
0x3c8d  dup
0x3c8e  ldc.i4.4
0x3c8f  ldstr    aCsv// ".csv"
0x3c94  stelem.ref
0x3c95  call     T0x2B000033
0x3c9a  ldloc.1
0x3c9b  ldftn    instance bool <>c__DisplayClass85_0::<CreateExcel>b__0(string e)
0x3ca1  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x3ca6  call     T0x2B000034
0x3cab  brfalse.s loc_3CBE
0x3cad  ldloc.1
0x3cae  ldfld    string <>c__DisplayClass85_0::fileExtension
0x3cb3  call     string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.RepLibRes::DisallowedResourceExtensionError(string)
0x3cb8  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ResourceFileFormatNotAllowedException::.ctor(string)
0x3cbd  throw
0x3cbe  ldarg.s  5
0x3cc0  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::HasContent()
0x3cc5  brtrue.s loc_3CD2
0x3cc7  call     string Microsoft.ReportingServices.Portal.Services.SR::get_Error_CatalogItemContentInvalid()
0x3ccc  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.ExcelWorkbookContentInvalidException::.ctor(string)
0x3cd1  throw
0x3cd2  ldarg.s  5
0x3cd4  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_ContentType()
0x3cd9  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3cde  brfalse.s loc_3CEC
0x3ce0  ldarg.s  5
0x3ce2  ldstr    aApplicationOct// "application/octet-stream"
0x3ce7  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_ContentType(string)
0x3cec  ldarg.1
0x3ced  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateExcelWorkbookAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_CreateExcelAction()
0x3cf2  dup
0x3cf3  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateExcelWorkbookActionParameters>::get_ActionParameters()
0x3cf8  stloc.2
0x3cf9  ldloc.2
0x3cfa  ldarg.s  5
0x3cfc  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x3d01  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_ItemName(string)
0x3d06  ldloc.2
0x3d07  ldarg.3
0x3d08  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_ParentPath(string)
0x3d0d  ldloc.2
0x3d0e  ldarg.s  4
0x3d10  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_Overwrite(bool)
0x3d15  ldloc.2
0x3d16  ldarg.s  5
0x3d18  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_ContentType()
0x3d1d  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateExcelWorkbookActionParameters::set_MimeType(string)
0x3d22  ldloc.2
0x3d23  ldarg.s  5
0x3d25  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemContent Microsoft.ReportingServices.Portal.Services.Extensions.CatalogItemExtensions::ToCatalogItemStreamContent(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem item)
0x3d2a  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemWithContentActionParameters::set_CatalogItemContent(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemContent)
0x3d2f  ldarg.s  6
0x3d31  brfalse.s loc_3D6D
0x3d33  ldarg.s  6
0x3d35  call     T0x2B000018
0x3d3a  brfalse.s loc_3D6D
0x3d3c  ldloc.2
0x3d3d  ldarg.s  6
0x3d3f  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property> <>c::<>9__85_1
0x3d44  dup
0x3d45  brtrue.s loc_3D5E
0x3d47  pop
0x3d48  ldsfld   class <>c <>c::<>9
0x3d4d  ldftn    instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property <>c::<CreateExcel>b__85_1(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property prop)
0x3d53  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::.ctor(object, native int)
0x3d58  dup
0x3d59  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property> <>c::<>9__85_1
0x3d5e  call     T0x2B000019
0x3d63  call     T0x2B00001A
0x3d68  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_Properties(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[])
0x3d6d  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateExcelWorkbookActionParameters>::Execute()
0x3d72  ldarg.0
0x3d73  ldarg.1
0x3d74  ldarg.2
0x3d75  ldarg.0
0x3d76  ldarg.3
0x3d77  ldarg.s  5
0x3d79  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x3d7e  call     instance string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::PathCombine(string path1, string path2)
0x3d83  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x3d88  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.ExcelWorkbook
0x3d8d  stloc.3
0x3d8e  leave.s  loc_3D9A
0x3d90  ldloc.0
0x3d91  brfalse.s loc_3D99
0x3d93  ldloc.0
0x3d94  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3d99  endfinally
0x3d9a  ldloc.3
0x3d9b  ret
```
