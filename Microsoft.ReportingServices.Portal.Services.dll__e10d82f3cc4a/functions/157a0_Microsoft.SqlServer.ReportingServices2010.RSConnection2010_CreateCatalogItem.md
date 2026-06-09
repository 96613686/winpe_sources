# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateCatalogItem

- ea: `0x157a0`
- end: `0x15807`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateCatalogItem`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x20db0`

## callees

- `0x23d30`

## string_xrefs

- `0x157e2`: `CreateCatalogItem`

## pseudocode

```c

```

## disassembly

```asm
0x157a0  newobj   instance void <>c__DisplayClass120_0::.ctor()
0x157a5  stloc.0
0x157a6  ldloc.0
0x157a7  ldarg.0
0x157a8  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass120_0::<>4__this
0x157ad  ldloc.0
0x157ae  ldarg.1
0x157af  stfld    string <>c__DisplayClass120_0::itemType
0x157b4  ldloc.0
0x157b5  ldarg.2
0x157b6  stfld    string <>c__DisplayClass120_0::name
0x157bb  ldloc.0
0x157bc  ldarg.3
0x157bd  stfld    string <>c__DisplayClass120_0::parent
0x157c2  ldloc.0
0x157c3  ldarg.s  4
0x157c5  stfld    bool <>c__DisplayClass120_0::overwrite
0x157ca  ldloc.0
0x157cb  ldarg.s  5
0x157cd  stfld    unsigned int8[] <>c__DisplayClass120_0::definition
0x157d2  ldloc.0
0x157d3  ldarg.s  6
0x157d5  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property[] <>c__DisplayClass120_0::properties
0x157da  ldloc.0
0x157db  ldnull
0x157dc  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Warning[] <>c__DisplayClass120_0::outWarnings
0x157e1  ldarg.0
0x157e2  ldstr    aCreatecatalogi// "CreateCatalogItem"
0x157e7  ldloc.0
0x157e8  ldftn    instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CatalogItem <>c__DisplayClass120_0::<CreateCatalogItem>b__0()
0x157ee  newobj   instance void class SoapMethod<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CatalogItem>::.ctor(object, native int)
0x157f3  newobj   instance void class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CatalogItem>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x157f8  callvirt instance var<u1> class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CatalogItem>::ExecuteMethod()
0x157fd  ldarg.s  7
0x157ff  ldloc.0
0x15800  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Warning[] <>c__DisplayClass120_0::outWarnings
0x15805  stind.ref
0x15806  ret
```
