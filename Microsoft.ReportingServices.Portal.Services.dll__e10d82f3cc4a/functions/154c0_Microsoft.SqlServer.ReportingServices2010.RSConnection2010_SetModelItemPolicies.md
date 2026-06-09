# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::SetModelItemPolicies

- ea: `0x154c0`
- end: `0x15500`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::SetModelItemPolicies`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x23a50`

## string_xrefs

- `0x154e3`: `SetModelItemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x154c0  newobj   instance void <>c__DisplayClass109_0::.ctor()
0x154c5  stloc.0
0x154c6  ldloc.0
0x154c7  ldarg.0
0x154c8  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass109_0::<>4__this
0x154cd  ldloc.0
0x154ce  ldarg.1
0x154cf  stfld    string <>c__DisplayClass109_0::model
0x154d4  ldloc.0
0x154d5  ldarg.2
0x154d6  stfld    string <>c__DisplayClass109_0::modelItemId
0x154db  ldloc.0
0x154dc  ldarg.3
0x154dd  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Policy[] <>c__DisplayClass109_0::policies
0x154e2  ldarg.0
0x154e3  ldstr    aSetmodelitempo// "SetModelItemPolicies"
0x154e8  ldloc.0
0x154e9  ldftn    instance int32 <>c__DisplayClass109_0::<SetModelItemPolicies>b__0()
0x154ef  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x154f4  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x154f9  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x154fe  pop
0x154ff  ret
```
