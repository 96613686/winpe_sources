# Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::ConvertToSystemResourceModel

- ea: `0xd3b0`
- end: `0xd49d`
- name: `Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::ConvertToSystemResourceModel`
- size: `237`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xcf50`
- `0xd020`
- `0x21be0`

## callees

- `0xd4c0`
- `0x21d60`

## pseudocode

```c

```

## disassembly

```asm
0xd3b0  newobj   instance void <>c__DisplayClass14_0::.ctor()
0xd3b5  stloc.0
0xd3b6  ldloc.0
0xd3b7  ldarg.0
0xd3b8  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource <>c__DisplayClass14_0::systemResource
0xd3bd  ldloc.0
0xd3be  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource::.ctor()
0xd3c3  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource <>c__DisplayClass14_0::resource
0xd3c8  ldloc.0
0xd3c9  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource <>c__DisplayClass14_0::resource
0xd3ce  ldloc.0
0xd3cf  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource <>c__DisplayClass14_0::systemResource
0xd3d4  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource::get_Name()
0xd3d9  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource::set_Name(string)
0xd3de  ldloc.0
0xd3df  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource <>c__DisplayClass14_0::resource
0xd3e4  ldloc.0
0xd3e5  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource <>c__DisplayClass14_0::systemResource
0xd3ea  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource::get_TypeName()
0xd3ef  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource::set_TypeName(string)
0xd3f4  ldloc.0
0xd3f5  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource <>c__DisplayClass14_0::resource
0xd3fa  ldloc.0
0xd3fb  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource <>c__DisplayClass14_0::systemResource
0xd400  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource::get_TypeName()
0xd405  call     valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResourceType Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::GetSystemResourceType(string typeName)
0xd40a  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource::set_Type(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResourceType)
0xd40f  ldloc.0
0xd410  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource <>c__DisplayClass14_0::resource
0xd415  ldloc.0
0xd416  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource <>c__DisplayClass14_0::systemResource
0xd41b  callvirt instance valuetype [mscorlib]System.Guid [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource::get_Id()
0xd420  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource::set_Id(valuetype [mscorlib]System.Guid)
0xd425  ldloc.0
0xd426  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource <>c__DisplayClass14_0::resource
0xd42b  ldloc.0
0xd42c  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource <>c__DisplayClass14_0::systemResource
0xd431  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource::get_Version()
0xd436  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource::set_Version(string)
0xd43b  ldloc.0
0xd43c  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource <>c__DisplayClass14_0::resource
0xd441  ldloc.0
0xd442  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource <>c__DisplayClass14_0::systemResource
0xd447  callvirt instance valuetype [mscorlib]System.Guid [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource::get_PackageId()
0xd44c  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource::set_PackageId(valuetype [mscorlib]System.Guid)
0xd451  ldloc.0
0xd452  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource <>c__DisplayClass14_0::resource
0xd457  ldloc.0
0xd458  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource <>c__DisplayClass14_0::systemResource
0xd45d  isinst   Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResource
0xd462  ldnull
0xd463  cgt.un
0xd465  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource::set_IsEmbedded(bool)
0xd46a  ldloc.0
0xd46b  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource <>c__DisplayClass14_0::resource
0xd470  ldloc.0
0xd471  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource <>c__DisplayClass14_0::systemResource
0xd476  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource::get_Items()
0xd47b  ldloc.0
0xd47c  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResourceItem <>c__DisplayClass14_0::<ConvertToSystemResourceModel>b__0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> i)
0xd482  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResourceItem>::.ctor(object, native int)
0xd487  call     T0x2B0000C0
0xd48c  call     T0x2B0000C1
0xd491  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource::set_Items(class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResourceItem[])
0xd496  ldloc.0
0xd497  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource <>c__DisplayClass14_0::resource
0xd49c  ret
```
