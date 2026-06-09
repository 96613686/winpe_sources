# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetCacheRefreshPlanProperties

- ea: `0x15bb0`
- end: `0x15c2f`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetCacheRefreshPlanProperties`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x24090`

## string_xrefs

- `0x15be8`: `GetCacheRefreshPlanProperties`

## pseudocode

```c

```

## disassembly

```asm
0x15bb0  newobj   instance void <>c__DisplayClass137_0::.ctor()
0x15bb5  stloc.0
0x15bb6  ldloc.0
0x15bb7  ldarg.0
0x15bb8  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass137_0::<>4__this
0x15bbd  ldloc.0
0x15bbe  ldarg.1
0x15bbf  stfld    string <>c__DisplayClass137_0::cacheRefreshPlanId
0x15bc4  ldloc.0
0x15bc5  ldnull
0x15bc6  stfld    string <>c__DisplayClass137_0::outLastRunStatus
0x15bcb  ldloc.0
0x15bcc  ldnull
0x15bcd  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CacheRefreshPlanState <>c__DisplayClass137_0::outState
0x15bd2  ldloc.0
0x15bd3  ldnull
0x15bd4  stfld    string <>c__DisplayClass137_0::outEventType
0x15bd9  ldloc.0
0x15bda  ldnull
0x15bdb  stfld    string <>c__DisplayClass137_0::outMatchData
0x15be0  ldloc.0
0x15be1  ldnull
0x15be2  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValue[] <>c__DisplayClass137_0::outParameters
0x15be7  ldarg.0
0x15be8  ldstr    aGetcacherefres// "GetCacheRefreshPlanProperties"
0x15bed  ldloc.0
0x15bee  ldftn    instance string <>c__DisplayClass137_0::<GetCacheRefreshPlanProperties>b__0()
0x15bf4  newobj   instance void class SoapMethod<string>::.ctor(object, native int)
0x15bf9  newobj   instance void class SoapMethodWrapper`1<string>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x15bfe  callvirt instance var<u1> class SoapMethodWrapper`1<string>::ExecuteMethod()
0x15c03  ldarg.2
0x15c04  ldloc.0
0x15c05  ldfld    string <>c__DisplayClass137_0::outLastRunStatus
0x15c0a  stind.ref
0x15c0b  ldarg.3
0x15c0c  ldloc.0
0x15c0d  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.CacheRefreshPlanState <>c__DisplayClass137_0::outState
0x15c12  stind.ref
0x15c13  ldarg.s  4
0x15c15  ldloc.0
0x15c16  ldfld    string <>c__DisplayClass137_0::outEventType
0x15c1b  stind.ref
0x15c1c  ldarg.s  5
0x15c1e  ldloc.0
0x15c1f  ldfld    string <>c__DisplayClass137_0::outMatchData
0x15c24  stind.ref
0x15c25  ldarg.s  6
0x15c27  ldloc.0
0x15c28  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValue[] <>c__DisplayClass137_0::outParameters
0x15c2d  stind.ref
0x15c2e  ret
```
