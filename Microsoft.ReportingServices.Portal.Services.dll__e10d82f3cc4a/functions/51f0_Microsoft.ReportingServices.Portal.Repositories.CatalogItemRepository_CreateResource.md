# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateResource

- ea: `0x51f0`
- end: `0x52bb`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateResource`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2530`

## callees

- `0x1ab0`
- `0x2240`
- `0x51f0`

## pseudocode

```c

```

## disassembly

```asm
0x51f0  ldarg.s  6
0x51f2  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_ContentType()
0x51f7  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x51fc  brfalse.s loc_520A
0x51fe  ldarg.s  6
0x5200  ldstr    aApplicationOct// "application/octet-stream"
0x5205  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_ContentType(string)
0x520a  ldarg.1
0x520b  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateResourceAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_CreateResourceAction()
0x5210  stloc.0
0x5211  ldloc.0
0x5212  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateResourceActionParameters>::get_ActionParameters()
0x5217  ldarg.3
0x5218  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_ItemName(string)
0x521d  ldloc.0
0x521e  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateResourceActionParameters>::get_ActionParameters()
0x5223  ldarg.s  4
0x5225  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_ParentPath(string)
0x522a  ldloc.0
0x522b  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateResourceActionParameters>::get_ActionParameters()
0x5230  ldarg.s  5
0x5232  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_Overwrite(bool)
0x5237  ldloc.0
0x5238  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateResourceActionParameters>::get_ActionParameters()
0x523d  ldarg.s  6
0x523f  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0x5244  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateResourceActionParameters::set_Content(unsigned int8[])
0x5249  ldloc.0
0x524a  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateResourceActionParameters>::get_ActionParameters()
0x524f  ldarg.s  6
0x5251  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_ContentType()
0x5256  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateResourceActionParameters::set_MimeType(string)
0x525b  ldarg.s  7
0x525d  brfalse.s loc_529E
0x525f  ldarg.s  7
0x5261  call     T0x2B000018
0x5266  brfalse.s loc_529E
0x5268  ldloc.0
0x5269  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateResourceActionParameters>::get_ActionParameters()
0x526e  ldarg.s  7
0x5270  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property> <>c::<>9__118_0
0x5275  dup
0x5276  brtrue.s loc_528F
0x5278  pop
0x5279  ldsfld   class <>c <>c::<>9
0x527e  ldftn    instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property <>c::<CreateResource>b__118_0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property prop)
0x5284  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::.ctor(object, native int)
0x5289  dup
0x528a  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property> <>c::<>9__118_0
0x528f  call     T0x2B000019
0x5294  call     T0x2B00001A
0x5299  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_Properties(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[])
0x529e  ldloc.0
0x529f  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateResourceActionParameters>::Execute()
0x52a4  ldarg.0
0x52a5  ldarg.1
0x52a6  ldarg.2
0x52a7  ldarg.0
0x52a8  ldarg.s  4
0x52aa  ldarg.3
0x52ab  call     instance string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::PathCombine(string path1, string path2)
0x52b0  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x52b5  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.Resource
0x52ba  ret
```
