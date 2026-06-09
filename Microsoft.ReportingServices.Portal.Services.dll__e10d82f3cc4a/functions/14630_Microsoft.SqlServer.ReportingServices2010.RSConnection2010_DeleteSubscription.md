# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::DeleteSubscription

- ea: `0x14630`
- end: `0x14662`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::DeleteSubscription`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x21090`

## callees

- `0x22d10`

## string_xrefs

- `0x14645`: `DeleteSubscription`

## pseudocode

```c

```

## disassembly

```asm
0x14630  newobj   instance void <>c__DisplayClass57_0::.ctor()
0x14635  stloc.0
0x14636  ldloc.0
0x14637  ldarg.0
0x14638  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass57_0::<>4__this
0x1463d  ldloc.0
0x1463e  ldarg.1
0x1463f  stfld    string <>c__DisplayClass57_0::subscriptionId
0x14644  ldarg.0
0x14645  ldstr    aDeletesubscrip// "DeleteSubscription"
0x1464a  ldloc.0
0x1464b  ldftn    instance int32 <>c__DisplayClass57_0::<DeleteSubscription>b__0()
0x14651  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x14656  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x1465b  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x14660  pop
0x14661  ret
```
