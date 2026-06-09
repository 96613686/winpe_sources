# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::ListCacheRefreshPlans

- ea: `0x15b20`
- end: `0x15b51`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::ListCacheRefreshPlans`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x24000`

## string_xrefs

- `0x15b35`: `ListCacheRefreshPlans`

## pseudocode

```c

```

## disassembly

```asm
0x15b20  newobj   instance void <>c__DisplayClass135_0::.ctor()
0x15b25  stloc.0
0x15b26  ldloc.0
0x15b27  ldarg.0
0x15b28  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass135_0::<>4__this
0x15b2d  ldloc.0
0x15b2e  ldarg.1
0x15b2f  stfld    string <>c__DisplayClass135_0::itemPath
0x15b34  ldarg.0
0x15b35  ldstr    aListcacherefre// "ListCacheRefreshPlans"
0x15b3a  ldloc.0
0x15b3b  ldftn    instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CacheRefreshPlan[] <>c__DisplayClass135_0::<ListCacheRefreshPlans>b__0()
0x15b41  newobj   instance void class SoapMethod<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CacheRefreshPlan[]>::.ctor(object, native int)
0x15b46  newobj   instance void class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CacheRefreshPlan[]>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x15b4b  callvirt instance var<u1> class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CacheRefreshPlan[]>::ExecuteMethod()
0x15b50  ret
```
