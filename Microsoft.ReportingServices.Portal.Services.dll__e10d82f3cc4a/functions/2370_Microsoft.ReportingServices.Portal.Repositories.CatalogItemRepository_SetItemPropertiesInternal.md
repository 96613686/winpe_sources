# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SetItemPropertiesInternal

- ea: `0x2370`
- end: `0x23e6`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SetItemPropertiesInternal`
- size: `118`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2350`
- `0x2360`
- `0x38d0`

## callees

- `0x2370`
- `0x4db0`
- `0x9e80`

## pseudocode

```c

```

## disassembly

```asm
0x2370  ldarg.1
0x2371  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x2376  stloc.0
0x2377  ldarg.0
0x2378  ldloc.0
0x2379  ldarg.2
0x237a  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ThrowIfRestrictedItemType(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string path)
0x237f  ldloc.0
0x2380  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_SetPropertiesAction()
0x2385  stloc.1
0x2386  ldloc.1
0x2387  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters>::get_ActionParameters()
0x238c  ldarg.2
0x238d  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters::set_ItemPath(string)
0x2392  ldloc.1
0x2393  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters>::get_ActionParameters()
0x2398  ldarg.s  4
0x239a  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters::set_IgnoreSecCheck(bool)
0x239f  ldarg.3
0x23a0  brfalse.s loc_23DF
0x23a2  ldarg.3
0x23a3  call     T0x2B000018
0x23a8  brfalse.s loc_23DF
0x23aa  ldloc.1
0x23ab  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters>::get_ActionParameters()
0x23b0  ldarg.3
0x23b1  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property> <>c::<>9__43_0
0x23b6  dup
0x23b7  brtrue.s loc_23D0
0x23b9  pop
0x23ba  ldsfld   class <>c <>c::<>9
0x23bf  ldftn    instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property <>c::<SetItemPropertiesInternal>b__43_0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property x)
0x23c5  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::.ctor(object, native int)
0x23ca  dup
0x23cb  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property> <>c::<>9__43_0
0x23d0  call     T0x2B000019
0x23d5  call     T0x2B00001A
0x23da  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters::set_Properties(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[])
0x23df  ldloc.1
0x23e0  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SetPropertiesActionParameters>::Execute()
0x23e5  ret
```
