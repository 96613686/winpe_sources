# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetItemCacheOptions

- ea: `0x2ee0`
- end: `0x2ff9`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetItemCacheOptions`
- size: `281`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1a90`
- `0x2ee0`
- `0x3160`
- `0x9e80`
- `0xf6a0`

## pseudocode

```c

```

## disassembly

```asm
0x2ee0  ldarg.0
0x2ee1  ldarg.1
0x2ee2  ldarg.2
0x2ee3  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x2ee8  ldarg.1
0x2ee9  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x2eee  stloc.0
0x2eef  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::.ctor()
0x2ef4  stloc.1
0x2ef5  call     bool Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SupportsSnapshots(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem item)
0x2efa  brfalse.s loc_2F64
0x2efc  ldloc.0
0x2efd  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetExecutionOptionsAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_GetExecutionOptionsAction()
0x2f02  stloc.3
0x2f03  ldloc.3
0x2f04  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters>::get_ActionParameters()
0x2f09  ldarg.2
0x2f0a  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters::set_ReportPath(string)
0x2f0f  ldloc.3
0x2f10  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters>::Execute()
0x2f15  ldloc.3
0x2f16  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters>::get_ActionParameters()
0x2f1b  callvirt instance valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ExecutionSettingEnum [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters::get_ExecutionSettings()
0x2f20  ldc.i4.1
0x2f21  bne.un.s loc_2F64
0x2f23  ldloc.1
0x2f24  ldc.i4.2
0x2f25  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::set_ExecutionType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ItemExecutionType)
0x2f2a  ldloc.3
0x2f2b  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters>::get_ActionParameters()
0x2f30  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinitionOrReference [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters::get_Schedule()
0x2f35  isinst   [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.NoSchedule
0x2f3a  brtrue.s loc_2F62
0x2f3c  ldloc.1
0x2f3d  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference::.ctor()
0x2f42  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::set_Expiration(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference)
0x2f47  ldloc.1
0x2f48  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::get_Expiration()
0x2f4d  ldloc.3
0x2f4e  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters>::get_ActionParameters()
0x2f53  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinitionOrReference [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters::get_Schedule()
0x2f58  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleReferenceExtensions::ToWebApi(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinitionOrReference scheduleReference)
0x2f5d  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference::set_Schedule(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference)
0x2f62  ldloc.1
0x2f63  ret
0x2f64  ldloc.0
0x2f65  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetCacheOptionsAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_GetCacheOptionsAction()
0x2f6a  stloc.2
0x2f6b  ldloc.2
0x2f6c  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetCacheOptionsActionParameters>::get_ActionParameters()
0x2f71  ldarg.2
0x2f72  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetCacheOptionsActionParameters::set_ReportPath(string)
0x2f77  ldloc.2
0x2f78  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetCacheOptionsActionParameters>::Execute()
0x2f7d  ldloc.2
0x2f7e  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetCacheOptionsActionParameters>::get_ActionParameters()
0x2f83  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetCacheOptionsActionParameters::get_CacheReport()
0x2f88  brfalse.s loc_2FF0
0x2f8a  ldloc.1
0x2f8b  ldc.i4.1
0x2f8c  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::set_ExecutionType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ItemExecutionType)
0x2f91  ldloc.1
0x2f92  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference::.ctor()
0x2f97  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::set_Expiration(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference)
0x2f9c  ldloc.2
0x2f9d  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetCacheOptionsActionParameters>::get_ActionParameters()
0x2fa2  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ExpirationDefinition [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetCacheOptionsActionParameters::get_Expiration()
0x2fa7  stloc.s  4
0x2fa9  ldloc.s  4
0x2fab  isinst   [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.TimeExpiration
0x2fb0  stloc.s  5
0x2fb2  ldloc.s  5
0x2fb4  brfalse.s loc_2FCA
0x2fb6  ldloc.1
0x2fb7  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::get_Expiration()
0x2fbc  ldloc.s  5
0x2fbe  ldfld    int32 [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.TimeExpiration::Minutes
0x2fc3  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference::set_Minutes(int32)
0x2fc8  br.s     loc_2FF7
0x2fca  ldloc.s  4
0x2fcc  isinst   [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleExpiration
0x2fd1  stloc.s  6
0x2fd3  ldloc.s  6
0x2fd5  brfalse.s loc_2FF7
0x2fd7  ldloc.1
0x2fd8  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::get_Expiration()
0x2fdd  ldloc.s  6
0x2fdf  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinitionOrReference [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleExpiration::Schedule
0x2fe4  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleReferenceExtensions::ToWebApi(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinitionOrReference scheduleReference)
0x2fe9  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference::set_Schedule(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference)
0x2fee  br.s     loc_2FF7
0x2ff0  ldloc.1
0x2ff1  ldc.i4.0
0x2ff2  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::set_ExecutionType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ItemExecutionType)
0x2ff7  ldloc.1
0x2ff8  ret
```
