# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateFolder

- ea: `0x15760`
- end: `0x1579f`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateFolder`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x23cf0`

## string_xrefs

- `0x15783`: `CreateFolder`

## pseudocode

```c

```

## disassembly

```asm
0x15760  newobj   instance void <>c__DisplayClass119_0::.ctor()
0x15765  stloc.0
0x15766  ldloc.0
0x15767  ldarg.0
0x15768  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass119_0::<>4__this
0x1576d  ldloc.0
0x1576e  ldarg.1
0x1576f  stfld    string <>c__DisplayClass119_0::folder
0x15774  ldloc.0
0x15775  ldarg.2
0x15776  stfld    string <>c__DisplayClass119_0::parent
0x1577b  ldloc.0
0x1577c  ldarg.3
0x1577d  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property[] <>c__DisplayClass119_0::properties
0x15782  ldarg.0
0x15783  ldstr    aCreatefolder// "CreateFolder"
0x15788  ldloc.0
0x15789  ldftn    instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CatalogItem <>c__DisplayClass119_0::<CreateFolder>b__0()
0x1578f  newobj   instance void class SoapMethod<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CatalogItem>::.ctor(object, native int)
0x15794  newobj   instance void class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CatalogItem>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x15799  callvirt instance var<u1> class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CatalogItem>::ExecuteMethod()
0x1579e  ret
```
