# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::SetCacheRefreshPlanProperties

- ea: `0x15c30`
- end: `0x15c80`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::SetCacheRefreshPlanProperties`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x21330`

## callees

- `0x240e0`

## string_xrefs

- `0x15c63`: `SetCacheRefreshPlanProperties`

## pseudocode

```c

```

## disassembly

```asm
0x15c30  newobj   instance void <>c__DisplayClass138_0::.ctor()
0x15c35  stloc.0
0x15c36  ldloc.0
0x15c37  ldarg.0
0x15c38  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass138_0::<>4__this
0x15c3d  ldloc.0
0x15c3e  ldarg.1
0x15c3f  stfld    string <>c__DisplayClass138_0::cacheRefreshPlanId
0x15c44  ldloc.0
0x15c45  ldarg.2
0x15c46  stfld    string <>c__DisplayClass138_0::description
0x15c4b  ldloc.0
0x15c4c  ldarg.3
0x15c4d  stfld    string <>c__DisplayClass138_0::eventType
0x15c52  ldloc.0
0x15c53  ldarg.s  4
0x15c55  stfld    string <>c__DisplayClass138_0::matchData
0x15c5a  ldloc.0
0x15c5b  ldarg.s  5
0x15c5d  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValue[] <>c__DisplayClass138_0::parameters
0x15c62  ldarg.0
0x15c63  ldstr    aSetcacherefres// "SetCacheRefreshPlanProperties"
0x15c68  ldloc.0
0x15c69  ldftn    instance int32 <>c__DisplayClass138_0::<SetCacheRefreshPlanProperties>b__0()
0x15c6f  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x15c74  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x15c79  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x15c7e  pop
0x15c7f  ret
```
