# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::ListScheduledItems

- ea: `0x14f80`
- end: `0x14fb1`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::ListScheduledItems`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x23570`

## string_xrefs

- `0x14f95`: `ListScheduledItems`

## pseudocode

```c

```

## disassembly

```asm
0x14f80  newobj   instance void <>c__DisplayClass88_0::.ctor()
0x14f85  stloc.0
0x14f86  ldloc.0
0x14f87  ldarg.0
0x14f88  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass88_0::<>4__this
0x14f8d  ldloc.0
0x14f8e  ldarg.1
0x14f8f  stfld    string <>c__DisplayClass88_0::scheduleId
0x14f94  ldarg.0
0x14f95  ldstr    aListscheduledi// "ListScheduledItems"
0x14f9a  ldloc.0
0x14f9b  ldftn    instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CatalogItem[] <>c__DisplayClass88_0::<ListScheduledItems>b__0()
0x14fa1  newobj   instance void class SoapMethod<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CatalogItem[]>::.ctor(object, native int)
0x14fa6  newobj   instance void class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CatalogItem[]>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x14fab  callvirt instance var<u1> class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CatalogItem[]>::ExecuteMethod()
0x14fb0  ret
```
