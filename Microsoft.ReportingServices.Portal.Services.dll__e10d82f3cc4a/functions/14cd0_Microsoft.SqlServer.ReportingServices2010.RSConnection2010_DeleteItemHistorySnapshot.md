# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::DeleteItemHistorySnapshot

- ea: `0x14cd0`
- end: `0x14d09`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::DeleteItemHistorySnapshot`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x232e0`

## string_xrefs

- `0x14cec`: `DeleteItemHistorySnapshot`

## pseudocode

```c

```

## disassembly

```asm
0x14cd0  newobj   instance void <>c__DisplayClass78_0::.ctor()
0x14cd5  stloc.0
0x14cd6  ldloc.0
0x14cd7  ldarg.0
0x14cd8  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass78_0::<>4__this
0x14cdd  ldloc.0
0x14cde  ldarg.1
0x14cdf  stfld    string <>c__DisplayClass78_0::itemPath
0x14ce4  ldloc.0
0x14ce5  ldarg.2
0x14ce6  stfld    string <>c__DisplayClass78_0::historyId
0x14ceb  ldarg.0
0x14cec  ldstr    aDeleteitemhist// "DeleteItemHistorySnapshot"
0x14cf1  ldloc.0
0x14cf2  ldftn    instance int32 <>c__DisplayClass78_0::<DeleteItemHistorySnapshot>b__0()
0x14cf8  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x14cfd  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x14d02  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x14d07  pop
0x14d08  ret
```
