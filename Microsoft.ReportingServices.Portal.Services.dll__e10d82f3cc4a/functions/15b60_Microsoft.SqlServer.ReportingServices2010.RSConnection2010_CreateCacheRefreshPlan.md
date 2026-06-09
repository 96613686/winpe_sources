# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateCacheRefreshPlan

- ea: `0x15b60`
- end: `0x15baf`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateCacheRefreshPlan`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x212e0`

## callees

- `0x24040`

## string_xrefs

- `0x15b93`: `CreateCacheRefreshPlan`

## pseudocode

```c

```

## disassembly

```asm
0x15b60  newobj   instance void <>c__DisplayClass136_0::.ctor()
0x15b65  stloc.0
0x15b66  ldloc.0
0x15b67  ldarg.0
0x15b68  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass136_0::<>4__this
0x15b6d  ldloc.0
0x15b6e  ldarg.1
0x15b6f  stfld    string <>c__DisplayClass136_0::itemPath
0x15b74  ldloc.0
0x15b75  ldarg.2
0x15b76  stfld    string <>c__DisplayClass136_0::description
0x15b7b  ldloc.0
0x15b7c  ldarg.3
0x15b7d  stfld    string <>c__DisplayClass136_0::eventType
0x15b82  ldloc.0
0x15b83  ldarg.s  4
0x15b85  stfld    string <>c__DisplayClass136_0::matchData
0x15b8a  ldloc.0
0x15b8b  ldarg.s  5
0x15b8d  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValue[] <>c__DisplayClass136_0::parameters
0x15b92  ldarg.0
0x15b93  ldstr    aCreatecacheref// "CreateCacheRefreshPlan"
0x15b98  ldloc.0
0x15b99  ldftn    instance string <>c__DisplayClass136_0::<CreateCacheRefreshPlan>b__0()
0x15b9f  newobj   instance void class SoapMethod<string>::.ctor(object, native int)
0x15ba4  newobj   instance void class SoapMethodWrapper`1<string>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x15ba9  callvirt instance var<u1> class SoapMethodWrapper`1<string>::ExecuteMethod()
0x15bae  ret
```
