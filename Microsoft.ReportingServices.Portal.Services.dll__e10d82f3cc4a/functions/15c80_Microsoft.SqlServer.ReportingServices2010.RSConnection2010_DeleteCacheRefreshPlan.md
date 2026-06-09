# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::DeleteCacheRefreshPlan

- ea: `0x15c80`
- end: `0x15cb2`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::DeleteCacheRefreshPlan`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x21380`

## callees

- `0x24130`

## string_xrefs

- `0x15c95`: `DeleteCacheRefreshPlan`

## pseudocode

```c

```

## disassembly

```asm
0x15c80  newobj   instance void <>c__DisplayClass139_0::.ctor()
0x15c85  stloc.0
0x15c86  ldloc.0
0x15c87  ldarg.0
0x15c88  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass139_0::<>4__this
0x15c8d  ldloc.0
0x15c8e  ldarg.1
0x15c8f  stfld    string <>c__DisplayClass139_0::cacheRefreshPlanId
0x15c94  ldarg.0
0x15c95  ldstr    aDeletecacheref// "DeleteCacheRefreshPlan"
0x15c9a  ldloc.0
0x15c9b  ldftn    instance int32 <>c__DisplayClass139_0::<DeleteCacheRefreshPlan>b__0()
0x15ca1  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x15ca6  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x15cab  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x15cb0  pop
0x15cb1  ret
```
