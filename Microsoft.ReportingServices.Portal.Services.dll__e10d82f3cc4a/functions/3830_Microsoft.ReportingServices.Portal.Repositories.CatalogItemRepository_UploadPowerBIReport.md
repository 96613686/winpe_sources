# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UploadPowerBIReport

- ea: `0x3830`
- end: `0x38c1`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UploadPowerBIReport`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x3810`
- `0x3830`
- `0x38d0`
- `0x4e10`
- `0x9e80`

## pseudocode

```c

```

## disassembly

```asm
0x3830  ldc.i4.3
0x3831  newarr   [mscorlib]System.String
0x3836  dup
0x3837  ldc.i4.0
0x3838  ldstr    aSql// "SQL"
0x383d  stelem.ref
0x383e  dup
0x383f  ldc.i4.1
0x3840  ldstr    aUploadpowerbir// "UploadPowerBIReport"
0x3845  stelem.ref
0x3846  dup
0x3847  ldc.i4.2
0x3848  ldarg.2
0x3849  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Name()
0x384e  stelem.ref
0x384f  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0x3854  stloc.0
0x3855  ldarg.0
0x3856  ldarg.2
0x3857  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x385c  ldarg.2
0x385d  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x3862  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ThrowIfRestrictedItemType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType type, string path)
0x3867  ldarg.0
0x3868  ldfld    class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IFileSizeRestrictions Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_fileSizeRestrictions
0x386d  ldarg.2
0x386e  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0x3873  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.IFileSizeRestrictions::ThrowIfSizeIsOutOfLimits(unsigned int8[])
0x3878  ldarg.1
0x3879  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x387e  stloc.1
0x387f  ldarg.0
0x3880  ldarg.2
0x3881  call     instance string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetPowerBiReportParentPath(class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport pbiReport)
0x3886  stloc.2
0x3887  ldc.i4.1
0x3888  stloc.3
0x3889  ldnull
0x388a  stloc.s  4
0x388c  ldarg.2
0x388d  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Properties()
0x3892  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>::get_Count()
0x3897  ldc.i4.0
0x3898  ble.s    loc_38A7
0x389a  ldarg.2
0x389b  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Properties()
0x38a0  call     T0x2B000020
0x38a5  stloc.s  4
0x38a7  ldarg.0
0x38a8  ldloc.1
0x38a9  ldarg.1
0x38aa  ldloc.2
0x38ab  ldloc.3
0x38ac  ldarg.2
0x38ad  ldloc.s  4
0x38af  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreatePowerBIReport(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string parentPath, bool overwrite, class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport item, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property[] properties)
0x38b4  leave.s  loc_38C0
0x38b6  ldloc.0
0x38b7  brfalse.s loc_38BF
0x38b9  ldloc.0
0x38ba  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38bf  endfinally
0x38c0  ret
```
