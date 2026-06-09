# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::UsesHanaOdbcProvider

- ea: `0xb030`
- end: `0xb070`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::UsesHanaOdbcProvider`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xaf90`

## callees

- `0xb030`

## pseudocode

```c

```

## disassembly

```asm
0xb030  ldarg.0
0xb031  callvirt instance string [mscorlib]System.String::ToLower()
0xb036  starg.s  0
0xb038  ldstr    aMsdasql// "msdasql"
0xb03d  stloc.0
0xb03e  ldstr    aMsdasql1// "msdasql.1"
0xb043  stloc.1
0xb044  ldstr    aHdbodbc// "hdbodbc"
0xb049  stloc.2
0xb04a  ldarg.0
0xb04b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb050  brtrue.s loc_B06E
0xb052  ldarg.0
0xb053  ldloc.2
0xb054  callvirt instance bool [mscorlib]System.String::Contains(string)
0xb059  brfalse.s loc_B06E
0xb05b  ldarg.0
0xb05c  ldloc.0
0xb05d  callvirt instance bool [mscorlib]System.String::Contains(string)
0xb062  brtrue.s loc_B06C
0xb064  ldarg.0
0xb065  ldloc.1
0xb066  callvirt instance bool [mscorlib]System.String::Contains(string)
0xb06b  ret
0xb06c  ldc.i4.1
0xb06d  ret
0xb06e  ldc.i4.0
0xb06f  ret
```
