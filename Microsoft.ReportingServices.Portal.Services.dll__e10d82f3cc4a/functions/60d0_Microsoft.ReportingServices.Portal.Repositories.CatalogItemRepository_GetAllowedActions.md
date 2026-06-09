# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetAllowedActions

- ea: `0x60d0`
- end: `0x613e`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetAllowedActions`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x60d0`
- `0x9e80`
- `0x9f00`

## string_xrefs

- `0x6111`: `Update Properties`
- `0x611c`: `Delete`
- `0x6127`: `Update Security Policies`

## pseudocode

```c

```

## disassembly

```asm
0x60d0  ldarg.1
0x60d1  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x60d6  stloc.0
0x60d7  ldloc.0
0x60d8  ldarg.2
0x60d9  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPermissionsAction Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateGetItemPermissionsAction(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string itemPath)
0x60de  dup
0x60df  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPermissionsActionParameters>::Execute()
0x60e4  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPermissionsActionParameters>::get_ActionParameters()
0x60e9  callvirt instance class [System]System.Collections.Specialized.StringCollection [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPermissionsActionParameters::get_Operations()
0x60ee  call     T0x2B00004E
0x60f3  stloc.1
0x60f4  ldloc.0
0x60f5  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_MyReportsEnabled()
0x60fa  brfalse.s loc_6137
0x60fc  ldarg.2
0x60fd  ldloc.0
0x60fe  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_PhysicalMyReportsPath()
0x6103  call     int32 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::CatalogCultureCompare(string, string)
0x6108  brtrue.s loc_6137
0x610a  ldloc.1
0x610b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x6110  dup
0x6111  ldstr    aUpdateProperti// "Update Properties"
0x6116  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x611b  dup
0x611c  ldstr    aDelete// "Delete"
0x6121  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6126  dup
0x6127  ldstr    aUpdateSecurity// "Update Security Policies"
0x612c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6131  call     T0x2B00004F
0x6136  stloc.1
0x6137  ldloc.1
0x6138  call     T0x2B000033
0x613d  ret
```
