# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::ListExtensions

- ea: `0x14a60`
- end: `0x14a91`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::ListExtensions`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x21450`

## callees

- `0x230a0`

## string_xrefs

- `0x14a75`: `ListExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x14a60  newobj   instance void <>c__DisplayClass68_0::.ctor()
0x14a65  stloc.0
0x14a66  ldloc.0
0x14a67  ldarg.0
0x14a68  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass68_0::<>4__this
0x14a6d  ldloc.0
0x14a6e  ldarg.1
0x14a6f  stfld    string <>c__DisplayClass68_0::extensionType
0x14a74  ldarg.0
0x14a75  ldstr    aListextensions// "ListExtensions"
0x14a7a  ldloc.0
0x14a7b  ldftn    instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Extension[] <>c__DisplayClass68_0::<ListExtensions>b__0()
0x14a81  newobj   instance void class SoapMethod<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Extension[]>::.ctor(object, native int)
0x14a86  newobj   instance void class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Extension[]>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x14a8b  callvirt instance var<u1> class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Extension[]>::ExecuteMethod()
0x14a90  ret
```
