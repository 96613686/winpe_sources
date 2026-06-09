# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateItemHistorySnapshot

- ea: `0x14c90`
- end: `0x14cd0`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateItemHistorySnapshot`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x21510`

## callees

- `0x232a0`

## string_xrefs

- `0x14cac`: `CreateItemHistorySnapshot`

## pseudocode

```c

```

## disassembly

```asm
0x14c90  newobj   instance void <>c__DisplayClass77_0::.ctor()
0x14c95  stloc.0
0x14c96  ldloc.0
0x14c97  ldarg.0
0x14c98  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass77_0::<>4__this
0x14c9d  ldloc.0
0x14c9e  ldarg.1
0x14c9f  stfld    string <>c__DisplayClass77_0::itemPath
0x14ca4  ldloc.0
0x14ca5  ldnull
0x14ca6  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Warning[] <>c__DisplayClass77_0::outWarnings
0x14cab  ldarg.0
0x14cac  ldstr    aCreateitemhist// "CreateItemHistorySnapshot"
0x14cb1  ldloc.0
0x14cb2  ldftn    instance string <>c__DisplayClass77_0::<CreateItemHistorySnapshot>b__0()
0x14cb8  newobj   instance void class SoapMethod<string>::.ctor(object, native int)
0x14cbd  newobj   instance void class SoapMethodWrapper`1<string>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x14cc2  callvirt instance var<u1> class SoapMethodWrapper`1<string>::ExecuteMethod()
0x14cc7  ldarg.2
0x14cc8  ldloc.0
0x14cc9  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Warning[] <>c__DisplayClass77_0::outWarnings
0x14cce  stind.ref
0x14ccf  ret
```
