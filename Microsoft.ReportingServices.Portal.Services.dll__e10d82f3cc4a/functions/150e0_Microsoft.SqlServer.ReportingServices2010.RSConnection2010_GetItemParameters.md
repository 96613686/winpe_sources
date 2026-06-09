# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetItemParameters

- ea: `0x150e0`
- end: `0x1512f`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetItemParameters`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x20e90`

## callees

- `0x236b0`

## string_xrefs

- `0x15113`: `GetItemParameters`

## pseudocode

```c

```

## disassembly

```asm
0x150e0  newobj   instance void <>c__DisplayClass94_0::.ctor()
0x150e5  stloc.0
0x150e6  ldloc.0
0x150e7  ldarg.0
0x150e8  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass94_0::<>4__this
0x150ed  ldloc.0
0x150ee  ldarg.1
0x150ef  stfld    string <>c__DisplayClass94_0::itemPath
0x150f4  ldloc.0
0x150f5  ldarg.2
0x150f6  stfld    string <>c__DisplayClass94_0::historyId
0x150fb  ldloc.0
0x150fc  ldarg.3
0x150fd  stfld    bool <>c__DisplayClass94_0::forRendering
0x15102  ldloc.0
0x15103  ldarg.s  4
0x15105  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValue[] <>c__DisplayClass94_0::values
0x1510a  ldloc.0
0x1510b  ldarg.s  5
0x1510d  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceCredentials[] <>c__DisplayClass94_0::credentials
0x15112  ldarg.0
0x15113  ldstr    aGetitemparamet// "GetItemParameters"
0x15118  ldloc.0
0x15119  ldftn    instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter[] <>c__DisplayClass94_0::<GetItemParameters>b__0()
0x1511f  newobj   instance void class SoapMethod<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter[]>::.ctor(object, native int)
0x15124  newobj   instance void class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter[]>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x15129  callvirt instance var<u1> class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter[]>::ExecuteMethod()
0x1512e  ret
```
