# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SetItemCacheOptions

- ea: `0x3000`
- end: `0x3153`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SetItemCacheOptions`
- size: `339`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1a90`
- `0x3000`
- `0x3160`
- `0x5c00`
- `0x9e80`
- `0xf710`

## pseudocode

```c

```

## disassembly

```asm
0x3000  ldarg.0
0x3001  ldarg.1
0x3002  ldarg.2
0x3003  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x3008  stloc.0
0x3009  ldarg.1
0x300a  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x300f  stloc.1
0x3010  ldloc.0
0x3011  call     bool Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SupportsSnapshots(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem item)
0x3016  brfalse  loc_30A2
0x301b  ldloc.1
0x301c  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetExecutionOptionsAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_SetExecutionOptionsAction()
0x3021  stloc.2
0x3022  ldloc.2
0x3023  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3028  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters>::set_BatchID(valuetype [mscorlib]System.Guid)
0x302d  ldloc.2
0x302e  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters>::get_ActionParameters()
0x3033  ldarg.2
0x3034  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters::set_ReportPath(string)
0x3039  ldarg.3
0x303a  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ItemExecutionType [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::get_ExecutionType()
0x303f  brfalse.s loc_3049
0x3041  ldarg.0
0x3042  ldarg.1
0x3043  ldloc.0
0x3044  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::EnsureCatalogItemDataSourcesValid(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem item)
0x3049  ldarg.3
0x304a  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ItemExecutionType [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::get_ExecutionType()
0x304f  ldc.i4.2
0x3050  bne.un.s loc_3090
0x3052  ldloc.2
0x3053  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters>::get_ActionParameters()
0x3058  ldc.i4.1
0x3059  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters::set_ExecutionSettings(valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ExecutionSettingEnum)
0x305e  ldarg.3
0x305f  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::get_Expiration()
0x3064  brfalse.s loc_309C
0x3066  ldarg.3
0x3067  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::get_Expiration()
0x306c  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference::get_Schedule()
0x3071  brfalse.s loc_309C
0x3073  ldloc.2
0x3074  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters>::get_ActionParameters()
0x3079  ldarg.3
0x307a  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::get_Expiration()
0x307f  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference::get_Schedule()
0x3084  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinitionOrReference Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleReferenceExtensions::ToSoapApi(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference scheduleReference)
0x3089  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters::set_Schedule(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinitionOrReference)
0x308e  br.s     loc_309C
0x3090  ldloc.2
0x3091  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters>::get_ActionParameters()
0x3096  ldc.i4.0
0x3097  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters::set_ExecutionSettings(valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ExecutionSettingEnum)
0x309c  ldloc.2
0x309d  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ExecutionOptionsActionParameters>::Execute()
0x30a2  ldarg.3
0x30a3  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ItemExecutionType [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::get_ExecutionType()
0x30a8  brfalse.s loc_30B6
0x30aa  ldarg.3
0x30ab  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ItemExecutionType [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::get_ExecutionType()
0x30b0  ldc.i4.1
0x30b1  bne.un   loc_3152
0x30b6  ldloc.1
0x30b7  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetCacheOptionsAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_SetCacheOptionsAction()
0x30bc  stloc.3
0x30bd  ldloc.3
0x30be  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x30c3  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetCacheOptionsActionParameters>::set_BatchID(valuetype [mscorlib]System.Guid)
0x30c8  ldloc.3
0x30c9  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetCacheOptionsActionParameters>::get_ActionParameters()
0x30ce  ldarg.2
0x30cf  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetCacheOptionsActionParameters::set_ReportPath(string)
0x30d4  ldarg.3
0x30d5  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ItemExecutionType [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::get_ExecutionType()
0x30da  ldc.i4.1
0x30db  bne.un.s loc_3140
0x30dd  ldloc.3
0x30de  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetCacheOptionsActionParameters>::get_ActionParameters()
0x30e3  ldc.i4.1
0x30e4  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetCacheOptionsActionParameters::set_CacheReport(bool)
0x30e9  ldarg.3
0x30ea  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::get_Expiration()
0x30ef  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference::get_Schedule()
0x30f4  brfalse.s loc_3123
0x30f6  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleExpiration::.ctor()
0x30fb  stloc.s  4
0x30fd  ldloc.s  4
0x30ff  ldarg.3
0x3100  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::get_Expiration()
0x3105  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference::get_Schedule()
0x310a  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinitionOrReference Microsoft.ReportingServices.Portal.Services.ODataExtensions.ScheduleReferenceExtensions::ToSoapApi(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference scheduleReference)
0x310f  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleDefinitionOrReference [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ScheduleExpiration::Schedule
0x3114  ldloc.3
0x3115  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetCacheOptionsActionParameters>::get_ActionParameters()
0x311a  ldloc.s  4
0x311c  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetCacheOptionsActionParameters::set_Expiration(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ExpirationDefinition)
0x3121  br.s     loc_314C
0x3123  ldloc.3
0x3124  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetCacheOptionsActionParameters>::get_ActionParameters()
0x3129  ldarg.3
0x312a  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheOptions::get_Expiration()
0x312f  callvirt instance int32 [Microsoft.ReportingServices.Portal.Interfaces]Model.ExpirationReference::get_Minutes()
0x3134  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.TimeExpiration [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.TimeExpiration::IntToThis(int32)
0x3139  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetCacheOptionsActionParameters::set_Expiration(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ExpirationDefinition)
0x313e  br.s     loc_314C
0x3140  ldloc.3
0x3141  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetCacheOptionsActionParameters>::get_ActionParameters()
0x3146  ldc.i4.0
0x3147  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetCacheOptionsActionParameters::set_CacheReport(bool)
0x314c  ldloc.3
0x314d  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetCacheOptionsActionParameters>::Execute()
0x3152  ret
```
