# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::SetItemParameters

- ea: `0x15130`
- end: `0x15169`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::SetItemParameters`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x20f40`

## callees

- `0x23700`

## string_xrefs

- `0x1514c`: `SetItemParameters`

## pseudocode

```c

```

## disassembly

```asm
0x15130  newobj   instance void <>c__DisplayClass95_0::.ctor()
0x15135  stloc.0
0x15136  ldloc.0
0x15137  ldarg.0
0x15138  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass95_0::<>4__this
0x1513d  ldloc.0
0x1513e  ldarg.1
0x1513f  stfld    string <>c__DisplayClass95_0::itemPath
0x15144  ldloc.0
0x15145  ldarg.2
0x15146  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ItemParameter[] <>c__DisplayClass95_0::parameters
0x1514b  ldarg.0
0x1514c  ldstr    aSetitemparamet// "SetItemParameters"
0x15151  ldloc.0
0x15152  ldftn    instance int32 <>c__DisplayClass95_0::<SetItemParameters>b__0()
0x15158  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x1515d  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x15162  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x15167  pop
0x15168  ret
```
