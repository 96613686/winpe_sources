# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateReportEditSession

- ea: `0x159a0`
- end: `0x159ef`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateReportEditSession`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbd50`

## callees

- `0x23e90`

## string_xrefs

- `0x159ca`: `CreateReportEditSession`

## pseudocode

```c

```

## disassembly

```asm
0x159a0  newobj   instance void <>c__DisplayClass130_0::.ctor()
0x159a5  stloc.0
0x159a6  ldloc.0
0x159a7  ldarg.0
0x159a8  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass130_0::<>4__this
0x159ad  ldloc.0
0x159ae  ldarg.1
0x159af  stfld    string <>c__DisplayClass130_0::report
0x159b4  ldloc.0
0x159b5  ldarg.2
0x159b6  stfld    string <>c__DisplayClass130_0::parent
0x159bb  ldloc.0
0x159bc  ldarg.3
0x159bd  stfld    unsigned int8[] <>c__DisplayClass130_0::definition
0x159c2  ldloc.0
0x159c3  ldnull
0x159c4  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Warning[] <>c__DisplayClass130_0::outWarnings
0x159c9  ldarg.0
0x159ca  ldstr    aCreatereported// "CreateReportEditSession"
0x159cf  ldloc.0
0x159d0  ldftn    instance string <>c__DisplayClass130_0::<CreateReportEditSession>b__0()
0x159d6  newobj   instance void class SoapMethod<string>::.ctor(object, native int)
0x159db  newobj   instance void class SoapMethodWrapper`1<string>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x159e0  callvirt instance var<u1> class SoapMethodWrapper`1<string>::ExecuteMethod()
0x159e5  ldarg.s  4
0x159e7  ldloc.0
0x159e8  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Warning[] <>c__DisplayClass130_0::outWarnings
0x159ed  stind.ref
0x159ee  ret
```
