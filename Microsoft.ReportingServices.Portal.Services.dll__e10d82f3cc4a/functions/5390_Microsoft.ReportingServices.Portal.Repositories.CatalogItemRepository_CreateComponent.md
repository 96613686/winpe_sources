# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateComponent

- ea: `0x5390`
- end: `0x542f`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CreateComponent`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2530`

## callees

- `0x1ab0`
- `0x2240`
- `0x5390`

## string_xrefs

- `0x5398`: `componentName`
- `0x5405`: `Component`

## pseudocode

```c

```

## disassembly

```asm
0x5390  ldarg.3
0x5391  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5396  brfalse.s loc_53A3
0x5398  ldstr    aComponentname// "componentName"
0x539d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x53a2  throw
0x53a3  ldarg.3
0x53a4  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x53a9  ldstr    aRsc// ".RSC"
0x53ae  ldc.i4.5
0x53af  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x53b4  brfalse.s loc_53BE
0x53b6  ldarg.3
0x53b7  call     string [mscorlib]System.IO.Path::GetFileNameWithoutExtension(string)
0x53bc  starg.s  3
0x53be  ldc.i4.0
0x53bf  newarr   [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property
0x53c4  stloc.0
0x53c5  ldarg.s  7
0x53c7  brfalse.s loc_53FC
0x53c9  ldarg.s  7
0x53cb  ldlen
0x53cc  brfalse.s loc_53FC
0x53ce  ldarg.s  7
0x53d0  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property> <>c::<>9__120_0
0x53d5  dup
0x53d6  brtrue.s loc_53EF
0x53d8  pop
0x53d9  ldsfld   class <>c <>c::<>9
0x53de  ldftn    instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property <>c::<CreateComponent>b__120_0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property prop)
0x53e4  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property>::.ctor(object, native int)
0x53e9  dup
0x53ea  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property> <>c::<>9__120_0
0x53ef  call     T0x2B00002A
0x53f4  call     T0x2B00002B
0x53f9  stloc.0
0x53fa  br.s     loc_53FE
0x53fc  ldnull
0x53fd  stloc.0
0x53fe  ldarg.0
0x53ff  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_soapRS2010Proxy
0x5404  ldarg.2
0x5405  ldstr    aComponent// "Component"
0x540a  ldarg.3
0x540b  ldarg.s  4
0x540d  ldarg.s  5
0x540f  ldarg.s  6
0x5411  ldloc.0
0x5412  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy::CreateCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal, string, string, string, bool, unsigned int8[], class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property[])
0x5417  pop
0x5418  ldarg.0
0x5419  ldarg.1
0x541a  ldarg.2
0x541b  ldarg.0
0x541c  ldarg.s  4
0x541e  ldarg.3
0x541f  call     instance string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::PathCombine(string path1, string path2)
0x5424  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x5429  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.Component
0x542e  ret
```
