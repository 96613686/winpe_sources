# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetModelItemPermissions

- ea: `0x15430`
- end: `0x15468`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetModelItemPermissions`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x239d0`

## string_xrefs

- `0x1544c`: `GetModelItemPermissions`

## pseudocode

```c

```

## disassembly

```asm
0x15430  newobj   instance void <>c__DisplayClass107_0::.ctor()
0x15435  stloc.0
0x15436  ldloc.0
0x15437  ldarg.0
0x15438  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass107_0::<>4__this
0x1543d  ldloc.0
0x1543e  ldarg.1
0x1543f  stfld    string <>c__DisplayClass107_0::model
0x15444  ldloc.0
0x15445  ldarg.2
0x15446  stfld    string <>c__DisplayClass107_0::modelItemId
0x1544b  ldarg.0
0x1544c  ldstr    aGetmodelitempe// "GetModelItemPermissions"
0x15451  ldloc.0
0x15452  ldftn    instance string[] <>c__DisplayClass107_0::<GetModelItemPermissions>b__0()
0x15458  newobj   instance void class SoapMethod<string[]>::.ctor(object, native int)
0x1545d  newobj   instance void class SoapMethodWrapper`1<string[]>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x15462  callvirt instance var<u1> class SoapMethodWrapper`1<string[]>::ExecuteMethod()
0x15467  ret
```
