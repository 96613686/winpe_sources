# Microsoft.ReportingServices.Diagnostics.Task::FromToXml

- ea: `0xd570`
- end: `0xd599`
- name: `Microsoft.ReportingServices.Diagnostics.Task::FromToXml`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xd120`
- `0xd530`
- `0xd570`
- `0xdd20`
- `0xe760`

## pseudocode

```c

```

## disassembly

```asm
0xd570  ldarg.0
0xd571  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd576  brtrue.s loc_D580
0xd578  ldarg.0
0xd579  call     bool Microsoft.ReportingServices.Diagnostics.Task::IsSharedSchedule(string xml)
0xd57e  brfalse.s loc_D582
0xd580  ldarg.0
0xd581  ret
0xd582  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd587  newobj   instance void Microsoft.ReportingServices.Diagnostics.Task::.ctor(valuetype [mscorlib]System.Guid id)
0xd58c  dup
0xd58d  ldarg.0
0xd58e  callvirt instance void Microsoft.ReportingServices.Diagnostics.Task::FromXml(string xml)
0xd593  callvirt instance string Microsoft.ReportingServices.Diagnostics.Task::ToXml()
0xd598  ret
```
