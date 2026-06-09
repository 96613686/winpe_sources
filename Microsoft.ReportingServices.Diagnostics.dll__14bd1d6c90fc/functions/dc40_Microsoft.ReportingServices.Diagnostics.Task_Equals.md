# Microsoft.ReportingServices.Diagnostics.Task::Equals

- ea: `0xdc40`
- end: `0xdd1a`
- name: `Microsoft.ReportingServices.Diagnostics.Task::Equals`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0xd830`
- `0xd890`
- `0xd8b0`
- `0xdc40`
- `0xf370`
- `0xf390`
- `0xf3e0`
- `0xf420`

## pseudocode

```c

```

## disassembly

```asm
0xdc40  ldc.i4.1
0xdc41  stloc.0
0xdc42  ldarg.1
0xdc43  isinst   Microsoft.ReportingServices.Diagnostics.Task
0xdc48  brtrue.s loc_DC4C
0xdc4a  ldc.i4.0
0xdc4b  ret
0xdc4c  ldarg.1
0xdc4d  castclass Microsoft.ReportingServices.Diagnostics.Task
0xdc52  stloc.1
0xdc53  ldloc.1
0xdc54  callvirt instance valuetype Microsoft.ReportingServices.Diagnostics.TaskFlags Microsoft.ReportingServices.Diagnostics.Task::get_Flags()
0xdc59  ldarg.0
0xdc5a  call     instance valuetype Microsoft.ReportingServices.Diagnostics.TaskFlags Microsoft.ReportingServices.Diagnostics.Task::get_Flags()
0xdc5f  beq.s    loc_DC68
0xdc61  ldc.i4.0
0xdc62  stloc.0
0xdc63  br       loc_DD18
0xdc68  ldloc.1
0xdc69  callvirt instance int64 Microsoft.ReportingServices.Diagnostics.Task::get_MaxRunTime()
0xdc6e  ldarg.0
0xdc6f  call     instance int64 Microsoft.ReportingServices.Diagnostics.Task::get_MaxRunTime()
0xdc74  beq.s    loc_DC7D
0xdc76  ldc.i4.0
0xdc77  stloc.0
0xdc78  br       loc_DD18
0xdc7d  ldloc.1
0xdc7e  callvirt instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdc83  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_EndDate()
0xdc88  ldarg.0
0xdc89  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdc8e  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_EndDate()
0xdc93  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xdc98  brfalse.s loc_DC9E
0xdc9a  ldc.i4.0
0xdc9b  stloc.0
0xdc9c  br.s     loc_DD18
0xdc9e  ldloc.1
0xdc9f  callvirt instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdca4  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_StartDate()
0xdca9  ldarg.0
0xdcaa  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdcaf  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_StartDate()
0xdcb4  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xdcb9  brfalse.s loc_DCBF
0xdcbb  ldc.i4.0
0xdcbc  stloc.0
0xdcbd  br.s     loc_DD18
0xdcbf  ldloc.1
0xdcc0  callvirt instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdcc5  callvirt instance valuetype Microsoft.ReportingServices.Diagnostics.RecurrenceType Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_RecurrenceType()
0xdcca  ldarg.0
0xdccb  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdcd0  callvirt instance valuetype Microsoft.ReportingServices.Diagnostics.RecurrenceType Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_RecurrenceType()
0xdcd5  beq.s    loc_DCDB
0xdcd7  ldc.i4.0
0xdcd8  stloc.0
0xdcd9  br.s     loc_DD18
0xdcdb  ldloc.1
0xdcdc  callvirt instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdce1  callvirt instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xdce6  brfalse.s loc_DD09
0xdce8  ldloc.1
0xdce9  callvirt instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdcee  callvirt instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xdcf3  ldarg.0
0xdcf4  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdcf9  callvirt instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xdcfe  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xdd03  brtrue.s loc_DD18
0xdd05  ldc.i4.0
0xdd06  stloc.0
0xdd07  br.s     loc_DD18
0xdd09  ldarg.0
0xdd0a  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xdd0f  callvirt instance class Microsoft.ReportingServices.Diagnostics.BaseTriggerData Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_TriggerData()
0xdd14  brfalse.s loc_DD18
0xdd16  ldc.i4.0
0xdd17  stloc.0
0xdd18  ldloc.0
0xdd19  ret
```
