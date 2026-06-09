# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateDataSet

- ea: `0x5040`
- end: `0x5101`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateDataSet`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2530`

## callees

- `0x1ab0`
- `0x2240`
- `0x5040`

## pseudocode

```c

```

## disassembly

```asm
0x5040  ldarg.3
0x5041  ldc.i4.8
0x5042  ldstr    aName// "Name"
0x5047  call     void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Global::CheckItemName(string, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType, string)
0x504c  ldarg.3
0x504d  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x5052  ldstr    aRsd_0// ".RSD"
0x5057  ldc.i4.5
0x5058  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x505d  brfalse.s loc_5067
0x505f  ldarg.3
0x5060  call     string [mscorlib]System.IO.Path::GetFileNameWithoutExtension(string)
0x5065  starg.s  3
0x5067  ldarg.1
0x5068  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateDataSetAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_CreateDataSetAction()
0x506d  stloc.0
0x506e  ldloc.0
0x506f  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateDataSetActionParameters>::get_ActionParameters()
0x5074  ldarg.3
0x5075  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_ItemName(string)
0x507a  ldloc.0
0x507b  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateDataSetActionParameters>::get_ActionParameters()
0x5080  ldarg.s  4
0x5082  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_ParentPath(string)
0x5087  ldloc.0
0x5088  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateDataSetActionParameters>::get_ActionParameters()
0x508d  ldarg.s  6
0x508f  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateDataSetActionParameters::set_DataSetDefinition(unsigned int8[])
0x5094  ldloc.0
0x5095  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateDataSetActionParameters>::get_ActionParameters()
0x509a  ldarg.s  5
0x509c  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_Overwrite(bool)
0x50a1  ldarg.s  7
0x50a3  brfalse.s loc_50E4
0x50a5  ldarg.s  7
0x50a7  call     T0x2B000018
0x50ac  brfalse.s loc_50E4
0x50ae  ldloc.0
0x50af  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateDataSetActionParameters>::get_ActionParameters()
0x50b4  ldarg.s  7
0x50b6  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property> <>c::<>9__116_0
0x50bb  dup
0x50bc  brtrue.s loc_50D5
0x50be  pop
0x50bf  ldsfld   class <>c <>c::<>9
0x50c4  ldftn    instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property <>c::<CreateDataSet>b__116_0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property prop)
0x50ca  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::.ctor(object, native int)
0x50cf  dup
0x50d0  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property> <>c::<>9__116_0
0x50d5  call     T0x2B000019
0x50da  call     T0x2B00001A
0x50df  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateItemActionParameters::set_Properties(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property[])
0x50e4  ldloc.0
0x50e5  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CreateDataSetActionParameters>::Execute()
0x50ea  ldarg.0
0x50eb  ldarg.1
0x50ec  ldarg.2
0x50ed  ldarg.0
0x50ee  ldarg.s  4
0x50f0  ldarg.3
0x50f1  call     instance string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::PathCombine(string path1, string path2)
0x50f6  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x50fb  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet
0x5100  ret
```
