# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateItemProperties

- ea: `0x3f30`
- end: `0x3f6f`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::UpdateItemProperties`
- size: `63`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1d770`
- `0x1d7f0`
- `0x1da30`
- `0x1dbf0`
- `0x1df70`
- `0x1e0b0`
- `0x1e1b0`

## callees

- `0x3f30`
- `0x4180`

## pseudocode

```c

```

## disassembly

```asm
0x3f30  ldarg.0
0x3f31  ldarg.2
0x3f32  ldloca.s 0
0x3f34  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ResolveCommonCatalogItemProperties(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem item, [out] class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[]& soapProperties)
0x3f39  ldarg.s  4
0x3f3b  brfalse.s loc_3F4B
0x3f3d  ldloc.0
0x3f3e  ldarg.s  4
0x3f40  call     T0x2B000035
0x3f45  call     T0x2B00001A
0x3f4a  stloc.0
0x3f4b  ldarg.1
0x3f4c  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_SetPropertiesAction()
0x3f51  dup
0x3f52  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters>::get_ActionParameters()
0x3f57  ldloc.0
0x3f58  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters::set_Properties(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[])
0x3f5d  dup
0x3f5e  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters>::get_ActionParameters()
0x3f63  ldarg.3
0x3f64  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters::set_ItemPath(string)
0x3f69  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters>::PerformActionNow()
0x3f6e  ret
```
