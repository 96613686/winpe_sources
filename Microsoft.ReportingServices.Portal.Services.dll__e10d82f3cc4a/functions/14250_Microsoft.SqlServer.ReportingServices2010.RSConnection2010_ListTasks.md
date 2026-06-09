# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::ListTasks

- ea: `0x14250`
- end: `0x14281`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::ListTasks`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x22980`

## string_xrefs

- `0x14265`: `ListTasks`

## pseudocode

```c

```

## disassembly

```asm
0x14250  newobj   instance void <>c__DisplayClass40_0::.ctor()
0x14255  stloc.0
0x14256  ldloc.0
0x14257  ldarg.0
0x14258  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass40_0::<>4__this
0x1425d  ldloc.0
0x1425e  ldarg.1
0x1425f  stfld    string <>c__DisplayClass40_0::scope
0x14264  ldarg.0
0x14265  ldstr    aListtasks// "ListTasks"
0x1426a  ldloc.0
0x1426b  ldftn    instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Task[] <>c__DisplayClass40_0::<ListTasks>b__0()
0x14271  newobj   instance void class SoapMethod<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Task[]>::.ctor(object, native int)
0x14276  newobj   instance void class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Task[]>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x1427b  callvirt instance var<u1> class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Task[]>::ExecuteMethod()
0x14280  ret
```
