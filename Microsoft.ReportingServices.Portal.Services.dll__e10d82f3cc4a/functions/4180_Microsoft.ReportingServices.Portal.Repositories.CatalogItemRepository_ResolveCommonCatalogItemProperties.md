# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ResolveCommonCatalogItemProperties

- ea: `0x4180`
- end: `0x41e1`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ResolveCommonCatalogItemProperties`
- size: `97`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3f30`
- `0x1d6e0`
- `0x1dd50`
- `0x1df70`

## callees

- `0x4180`

## pseudocode

```c

```

## disassembly

```asm
0x4180  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::.ctor()
0x4185  dup
0x4186  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x418b  dup
0x418c  ldstr    aDescription// "Description"
0x4191  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x4196  dup
0x4197  ldarg.1
0x4198  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Description()
0x419d  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x41a2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x41a7  dup
0x41a8  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x41ad  dup
0x41ae  ldstr    aHidden// "Hidden"
0x41b3  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x41b8  dup
0x41b9  ldarg.1
0x41ba  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Hidden()
0x41bf  brtrue.s loc_41C8
0x41c1  ldstr    aFalse// "false"
0x41c6  br.s     loc_41CD
0x41c8  ldstr    aTrue// "true"
0x41cd  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x41d2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x41d7  stloc.0
0x41d8  ldarg.2
0x41d9  ldloc.0
0x41da  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::ToArray()
0x41df  stind.ref
0x41e0  ret
```
