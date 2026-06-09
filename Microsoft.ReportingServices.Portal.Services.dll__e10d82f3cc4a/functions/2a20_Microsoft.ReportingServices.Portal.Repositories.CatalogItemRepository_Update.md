# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::Update

- ea: `0x2a20`
- end: `0x2c16`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::Update`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2c20`

## callees

- `0x1a90`
- `0x2a20`
- `0x35b0`
- `0x3b00`
- `0x3da0`
- `0x3e40`
- `0x3e80`
- `0x3f70`
- `0x3ff0`
- `0x40e0`
- `0x49e0`
- `0x4b50`
- `0x4e10`
- `0x5110`
- `0x52c0`
- `0x5450`
- `0x9e80`

## string_xrefs

- `0x2bf9`: `Update for type `

## pseudocode

```c

```

## disassembly

```asm
0x2a20  ldarg.0
0x2a21  ldarg.3
0x2a22  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x2a27  ldarg.3
0x2a28  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x2a2d  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ThrowIfRestrictedItemType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType type, string path)
0x2a32  ldarg.0
0x2a33  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IFileSizeRestrictions Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_fileSizeRestrictions
0x2a38  ldarg.3
0x2a39  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0x2a3e  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IFileSizeRestrictions::ThrowIfSizeIsOutOfLimits(unsigned int8[])
0x2a43  ldarg.1
0x2a44  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x2a49  stloc.0
0x2a4a  ldarg.3
0x2a4b  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::ComputeParentPath()
0x2a50  stloc.1
0x2a51  ldarg.0
0x2a52  ldarg.1
0x2a53  ldarg.2
0x2a54  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x2a59  stloc.2
0x2a5a  ldloc.2
0x2a5b  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::ComputeParentPath()
0x2a60  stloc.3
0x2a61  ldarg.3
0x2a62  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Description()
0x2a67  brtrue.s loc_2A75
0x2a69  ldarg.3
0x2a6a  ldloc.2
0x2a6b  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Description()
0x2a70  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_Description(string)
0x2a75  ldloc.3
0x2a76  ldloc.1
0x2a77  ldc.i4.5
0x2a78  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2a7d  ldc.i4.0
0x2a7e  cgt.un
0x2a80  dup
0x2a81  brfalse.s loc_2A8E
0x2a83  ldarg.0
0x2a84  ldloc.0
0x2a85  ldloc.1
0x2a86  ldarg.3
0x2a87  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::EnsureCatalogItemCanBeCreated(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string parentPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem item)
0x2a8c  br.s     loc_2A99
0x2a8e  ldarg.0
0x2a8f  ldloc.0
0x2a90  ldloc.3
0x2a91  ldloc.2
0x2a92  ldloc.1
0x2a93  ldarg.3
0x2a94  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::EnsureCatalogItemCanBeEdited(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string originalParentPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem originalItem, string newParentPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem newCatalogItem)
0x2a99  brtrue.s loc_2AB2
0x2a9b  ldloc.2
0x2a9c  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x2aa1  ldarg.3
0x2aa2  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x2aa7  ldc.i4.4
0x2aa8  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2aad  ldc.i4.0
0x2aae  cgt.un
0x2ab0  br.s     loc_2AB3
0x2ab2  ldc.i4.1
0x2ab3  stloc.s  4
0x2ab5  ldarg.3
0x2ab6  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x2abb  stloc.s  5
0x2abd  ldloc.s  5
0x2abf  ldc.i4.1
0x2ac0  sub
0x2ac1  switch   loc_2AFB, loc_2B3B, loc_2B9A, loc_2BAE, loc_2BE5, loc_2BC2, loc_2B0D, loc_2B24, loc_2B52, loc_2BD1, loc_2B69, loc_2B86
0x2af6  br       loc_2BF9
0x2afb  ldarg.0
0x2afc  ldloc.0
0x2afd  ldarg.2
0x2afe  ldarg.3
0x2aff  ldloc.s  4
0x2b01  ldarg.s  4
0x2b03  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateFolder(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string origItemPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem folderItem, bool renameOrMove, string[] delta)
0x2b08  br       loc_2C14
0x2b0d  ldarg.0
0x2b0e  ldloc.0
0x2b0f  ldarg.2
0x2b10  ldarg.3
0x2b11  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi
0x2b16  ldloc.s  4
0x2b18  ldarg.s  4
0x2b1a  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateKpi(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string origItemPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi item, bool renameOrMove, string[] delta)
0x2b1f  br       loc_2C14
0x2b24  ldarg.0
0x2b25  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x2b2a  ldc.i4.3
0x2b2b  ldstr    aMobileReportUp// "Mobile Report updating is not supported"...
0x2b30  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2b35  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0x2b3a  throw
0x2b3b  ldarg.0
0x2b3c  ldarg.1
0x2b3d  ldarg.2
0x2b3e  ldarg.3
0x2b3f  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.Report
0x2b44  ldloc.s  4
0x2b46  ldarg.s  4
0x2b48  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateReport(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string origItemPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report item, bool renameOrMove, string[] delta)
0x2b4d  br       loc_2C14
0x2b52  ldarg.0
0x2b53  ldloc.0
0x2b54  ldarg.2
0x2b55  ldarg.3
0x2b56  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport
0x2b5b  ldloc.s  4
0x2b5d  ldarg.s  4
0x2b5f  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateLinkedReport(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string origItemPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport item, bool renameOrMove, string[] delta)
0x2b64  br       loc_2C14
0x2b69  ldarg.0
0x2b6a  ldarg.1
0x2b6b  ldarg.2
0x2b6c  ldloc.2
0x2b6d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0x2b72  ldarg.3
0x2b73  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport
0x2b78  ldloc.s  4
0x2b7a  ldarg.s  4
0x2b7c  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdatePowerBIReport(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string origItemPath, valuetype [mscorlib]System.Guid origItemId, class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport item, bool renameOrMove, string[] delta)
0x2b81  br       loc_2C14
0x2b86  ldarg.0
0x2b87  ldloc.0
0x2b88  ldarg.2
0x2b89  ldarg.3
0x2b8a  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.ExcelWorkbook
0x2b8f  ldloc.s  4
0x2b91  ldarg.s  4
0x2b93  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateExcel(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string origItemPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExcelWorkbook item, bool renameOrMove, string[] delta)
0x2b98  br.s     loc_2C14
0x2b9a  ldarg.0
0x2b9b  ldarg.1
0x2b9c  ldarg.2
0x2b9d  ldarg.3
0x2b9e  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource
0x2ba3  ldloc.s  4
0x2ba5  ldarg.s  4
0x2ba7  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateDataSource(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string origItemPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource dataSource, bool renameOrMove, string[] updatedFields)
0x2bac  br.s     loc_2C14
0x2bae  ldarg.0
0x2baf  ldarg.1
0x2bb0  ldarg.2
0x2bb1  ldarg.3
0x2bb2  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet
0x2bb7  ldloc.s  4
0x2bb9  ldarg.s  4
0x2bbb  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateDataSet(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string origItemPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet item, bool renameOrMove, string[] delta)
0x2bc0  br.s     loc_2C14
0x2bc2  ldarg.0
0x2bc3  ldloc.0
0x2bc4  ldarg.2
0x2bc5  ldarg.3
0x2bc6  ldloc.s  4
0x2bc8  ldarg.s  4
0x2bca  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateResource(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string origItemPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem item, bool renameOrMove, string[] delta)
0x2bcf  br.s     loc_2C14
0x2bd1  ldarg.0
0x2bd2  ldarg.1
0x2bd3  ldarg.2
0x2bd4  ldarg.3
0x2bd5  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportModel
0x2bda  ldloc.s  4
0x2bdc  ldarg.s  4
0x2bde  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateReportModel(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string origItemPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportModel reportModel, bool renameOrMove, string[] updatedFields)
0x2be3  br.s     loc_2C14
0x2be5  ldarg.0
0x2be6  ldarg.1
0x2be7  ldarg.2
0x2be8  ldarg.3
0x2be9  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.Component
0x2bee  ldloc.s  4
0x2bf0  ldarg.s  4
0x2bf2  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateComponent(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string origItemPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Component item, bool renameOrMove, string[] delta)
0x2bf7  br.s     loc_2C14
0x2bf9  ldstr    aUpdateForType// "Update for type "
0x2bfe  ldarg.3
0x2bff  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x2c04  box      [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType
0x2c09  call     string [mscorlib]System.String::Concat(object, object)
0x2c0e  newobj   instance void [mscorlib]System.NotImplementedException::.ctor(string)
0x2c13  throw
0x2c14  ldc.i4.1
0x2c15  ret
```
