# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateSchedule

- ea: `0x14ec0`
- end: `0x14eff`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateSchedule`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x21660`

## callees

- `0x234b0`

## string_xrefs

- `0x14ee3`: `CreateSchedule`

## pseudocode

```c

```

## disassembly

```asm
0x14ec0  newobj   instance void <>c__DisplayClass85_0::.ctor()
0x14ec5  stloc.0
0x14ec6  ldloc.0
0x14ec7  ldarg.0
0x14ec8  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass85_0::<>4__this
0x14ecd  ldloc.0
0x14ece  ldarg.1
0x14ecf  stfld    string <>c__DisplayClass85_0::name
0x14ed4  ldloc.0
0x14ed5  ldarg.2
0x14ed6  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ScheduleDefinition <>c__DisplayClass85_0::scheduleDefinition
0x14edb  ldloc.0
0x14edc  ldarg.3
0x14edd  stfld    string <>c__DisplayClass85_0::site
0x14ee2  ldarg.0
0x14ee3  ldstr    aCreateschedule// "CreateSchedule"
0x14ee8  ldloc.0
0x14ee9  ldftn    instance string <>c__DisplayClass85_0::<CreateSchedule>b__0()
0x14eef  newobj   instance void class SoapMethod<string>::.ctor(object, native int)
0x14ef4  newobj   instance void class SoapMethodWrapper`1<string>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x14ef9  callvirt instance var<u1> class SoapMethodWrapper`1<string>::ExecuteMethod()
0x14efe  ret
```
