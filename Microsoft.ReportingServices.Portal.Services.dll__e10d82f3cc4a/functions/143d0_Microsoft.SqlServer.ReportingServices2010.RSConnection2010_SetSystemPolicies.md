# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::SetSystemPolicies

- ea: `0x143d0`
- end: `0x14402`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::SetSystemPolicies`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x22ad0`

## string_xrefs

- `0x143e5`: `SetSystemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x143d0  newobj   instance void <>c__DisplayClass47_0::.ctor()
0x143d5  stloc.0
0x143d6  ldloc.0
0x143d7  ldarg.0
0x143d8  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass47_0::<>4__this
0x143dd  ldloc.0
0x143de  ldarg.1
0x143df  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Policy[] <>c__DisplayClass47_0::policies
0x143e4  ldarg.0
0x143e5  ldstr    aSetsystempolic// "SetSystemPolicies"
0x143ea  ldloc.0
0x143eb  ldftn    instance int32 <>c__DisplayClass47_0::<SetSystemPolicies>b__0()
0x143f1  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x143f6  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x143fb  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x14400  pop
0x14401  ret
```
