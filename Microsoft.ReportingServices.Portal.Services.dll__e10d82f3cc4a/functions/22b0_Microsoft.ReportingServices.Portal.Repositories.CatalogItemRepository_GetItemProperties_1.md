# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetItemProperties_1

- ea: `0x22b0`
- end: `0x2346`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetItemProperties_1`
- size: `150`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2270`
- `0x2290`

## callees

- `0x22b0`
- `0x4db0`

## pseudocode

```c

```

## disassembly

```asm
0x22b0  ldarg.0
0x22b1  ldarg.1
0x22b2  ldarg.2
0x22b3  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ThrowIfRestrictedItemType(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string path)
0x22b8  ldarg.1
0x22b9  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPropertiesAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_GetPropertiesAction()
0x22be  stloc.0
0x22bf  ldloc.0
0x22c0  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPropertiesActionParameters>::get_ActionParameters()
0x22c5  ldarg.2
0x22c6  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPropertiesActionParameters::set_ItemPath(string)
0x22cb  ldarg.3
0x22cc  brfalse.s loc_230B
0x22ce  ldarg.3
0x22cf  call     T0x2B000018
0x22d4  brfalse.s loc_230B
0x22d6  ldloc.0
0x22d7  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPropertiesActionParameters>::get_ActionParameters()
0x22dc  ldarg.3
0x22dd  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property> <>c::<>9__40_0
0x22e2  dup
0x22e3  brtrue.s loc_22FC
0x22e5  pop
0x22e6  ldsfld   class <>c <>c::<>9
0x22eb  ldftn    instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property <>c::<GetItemProperties>b__40_0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property x)
0x22f1  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::.ctor(object, native int)
0x22f6  dup
0x22f7  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property> <>c::<>9__40_0
0x22fc  call     T0x2B000019
0x2301  call     T0x2B00001A
0x2306  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPropertiesActionParameters::set_RequestedProperties(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[])
0x230b  ldloc.0
0x230c  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPropertiesActionParameters>::Execute()
0x2311  ldloc.0
0x2312  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPropertiesActionParameters>::get_ActionParameters()
0x2317  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[] [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetPropertiesActionParameters::get_PropertyValues()
0x231c  ldsfld   class [mscorlib]System.Func`2<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> <>c::<>9__40_1
0x2321  dup
0x2322  brtrue.s loc_233B
0x2324  pop
0x2325  ldsfld   class <>c <>c::<>9
0x232a  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property <>c::<GetItemProperties>b__40_1(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property x)
0x2330  newobj   instance void class [mscorlib]System.Func`2<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>::.ctor(object, native int)
0x2335  dup
0x2336  stsfld   class [mscorlib]System.Func`2<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> <>c::<>9__40_1
0x233b  call     T0x2B00001B
0x2340  call     T0x2B00001C
0x2345  ret
```
