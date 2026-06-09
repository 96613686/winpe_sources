# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateDataSource

- ea: `0x15710`
- end: `0x1575f`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateDataSource`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x23ca0`

## string_xrefs

- `0x15743`: `CreateDataSource`

## pseudocode

```c

```

## disassembly

```asm
0x15710  newobj   instance void <>c__DisplayClass118_0::.ctor()
0x15715  stloc.0
0x15716  ldloc.0
0x15717  ldarg.0
0x15718  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass118_0::<>4__this
0x1571d  ldloc.0
0x1571e  ldarg.1
0x1571f  stfld    string <>c__DisplayClass118_0::dataSource
0x15724  ldloc.0
0x15725  ldarg.2
0x15726  stfld    string <>c__DisplayClass118_0::parent
0x1572b  ldloc.0
0x1572c  ldarg.3
0x1572d  stfld    bool <>c__DisplayClass118_0::overwrite
0x15732  ldloc.0
0x15733  ldarg.s  4
0x15735  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinition <>c__DisplayClass118_0::definition
0x1573a  ldloc.0
0x1573b  ldarg.s  5
0x1573d  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property[] <>c__DisplayClass118_0::properties
0x15742  ldarg.0
0x15743  ldstr    aCreatedatasour// "CreateDataSource"
0x15748  ldloc.0
0x15749  ldftn    instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CatalogItem <>c__DisplayClass118_0::<CreateDataSource>b__0()
0x1574f  newobj   instance void class SoapMethod<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CatalogItem>::.ctor(object, native int)
0x15754  newobj   instance void class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CatalogItem>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x15759  callvirt instance var<u1> class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CatalogItem>::ExecuteMethod()
0x1575e  ret
```
