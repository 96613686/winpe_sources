# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::DeleteSchedule

- ea: `0x14f00`
- end: `0x14f32`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::DeleteSchedule`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x21620`

## callees

- `0x234f0`

## string_xrefs

- `0x14f15`: `DeleteSchedule`

## pseudocode

```c

```

## disassembly

```asm
0x14f00  newobj   instance void <>c__DisplayClass86_0::.ctor()
0x14f05  stloc.0
0x14f06  ldloc.0
0x14f07  ldarg.0
0x14f08  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass86_0::<>4__this
0x14f0d  ldloc.0
0x14f0e  ldarg.1
0x14f0f  stfld    string <>c__DisplayClass86_0::scheduleId
0x14f14  ldarg.0
0x14f15  ldstr    aDeleteschedule// "DeleteSchedule"
0x14f1a  ldloc.0
0x14f1b  ldftn    instance int32 <>c__DisplayClass86_0::<DeleteSchedule>b__0()
0x14f21  newobj   instance void class SoapMethod<int32>::.ctor(object, native int)
0x14f26  newobj   instance void class SoapMethodWrapper`1<int32>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x14f2b  callvirt instance var<u1> class SoapMethodWrapper`1<int32>::ExecuteMethod()
0x14f30  pop
0x14f31  ret
```
