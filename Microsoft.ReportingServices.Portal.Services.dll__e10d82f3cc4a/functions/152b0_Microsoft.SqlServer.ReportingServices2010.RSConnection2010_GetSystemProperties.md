# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetSystemProperties

- ea: `0x152b0`
- end: `0x152e1`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetSystemProperties`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x23880`

## string_xrefs

- `0x152c5`: `GetSystemProperties`

## pseudocode

```c

```

## disassembly

```asm
0x152b0  newobj   instance void <>c__DisplayClass101_0::.ctor()
0x152b5  stloc.0
0x152b6  ldloc.0
0x152b7  ldarg.0
0x152b8  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass101_0::<>4__this
0x152bd  ldloc.0
0x152be  ldarg.1
0x152bf  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property[] <>c__DisplayClass101_0::properties
0x152c4  ldarg.0
0x152c5  ldstr    aGetsystemprope// "GetSystemProperties"
0x152ca  ldloc.0
0x152cb  ldftn    instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property[] <>c__DisplayClass101_0::<GetSystemProperties>b__0()
0x152d1  newobj   instance void class SoapMethod<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property[]>::.ctor(object, native int)
0x152d6  newobj   instance void class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property[]>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x152db  callvirt instance var<u1> class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Property[]>::ExecuteMethod()
0x152e0  ret
```
