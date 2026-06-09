# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetReportServerConfigInfo

- ea: `0x15960`
- end: `0x15991`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetReportServerConfigInfo`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x23e50`

## string_xrefs

- `0x15975`: `GetReportServerConfigInfo`

## pseudocode

```c

```

## disassembly

```asm
0x15960  newobj   instance void <>c__DisplayClass129_0::.ctor()
0x15965  stloc.0
0x15966  ldloc.0
0x15967  ldarg.0
0x15968  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass129_0::<>4__this
0x1596d  ldloc.0
0x1596e  ldarg.1
0x1596f  stfld    bool <>c__DisplayClass129_0::scaleOut
0x15974  ldarg.0
0x15975  ldstr    aGetreportserve// "GetReportServerConfigInfo"
0x1597a  ldloc.0
0x1597b  ldftn    instance string <>c__DisplayClass129_0::<GetReportServerConfigInfo>b__0()
0x15981  newobj   instance void class SoapMethod<string>::.ctor(object, native int)
0x15986  newobj   instance void class SoapMethodWrapper`1<string>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x1598b  callvirt instance var<u1> class SoapMethodWrapper`1<string>::ExecuteMethod()
0x15990  ret
```
