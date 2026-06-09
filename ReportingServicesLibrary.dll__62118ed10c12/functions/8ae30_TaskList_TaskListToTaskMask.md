# TaskList::TaskListToTaskMask

- ea: `0x8ae30`
- end: `0x8aeb2`
- name: `TaskList::TaskListToTaskMask`
- size: `130`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x3d080`
- `0x3d660`
- `0x59830`

## callees

- `0x4be20`
- `0x8ad30`
- `0x8ad60`
- `0x8ad70`
- `0x8ae30`

## string_xrefs

- `0x8ae41`: `TaskID`
- `0x8ae6c`: `TaskID`

## pseudocode

```c

```

## disassembly

```asm
0x8ae30  ldarg.0
0x8ae31  ldlen
0x8ae32  conv.i4
0x8ae33  ldc.i4.1
0x8ae34  bge.s    loc_8AE3C
0x8ae36  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.EmptyRoleException::.ctor()
0x8ae3b  throw
0x8ae3c  ldarg.0
0x8ae3d  ldc.i4.0
0x8ae3e  ldelem.ref
0x8ae3f  brtrue.s loc_8AE4C
0x8ae41  ldstr    aTaskid// "TaskID"
0x8ae46  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x8ae4b  throw
0x8ae4c  ldarg.0
0x8ae4d  ldc.i4.0
0x8ae4e  ldelem.ref
0x8ae4f  call     class SecurityTask Microsoft.ReportingServices.Library.AuthzData::FindTaskByID(string id)
0x8ae54  stloc.0
0x8ae55  ldloc.0
0x8ae56  callvirt instance char[] SecurityTask::GetEmptyMask()
0x8ae5b  stloc.1
0x8ae5c  ldloc.0
0x8ae5d  ldloc.1
0x8ae5e  callvirt instance void SecurityTask::IncludeMyselfInMask(char[] mask)
0x8ae63  ldc.i4.1
0x8ae64  stloc.2
0x8ae65  br.s     loc_8AE9D
0x8ae67  ldarg.0
0x8ae68  ldloc.2
0x8ae69  ldelem.ref
0x8ae6a  brtrue.s loc_8AE77
0x8ae6c  ldstr    aTaskid// "TaskID"
0x8ae71  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x8ae76  throw
0x8ae77  ldarg.0
0x8ae78  ldloc.2
0x8ae79  ldelem.ref
0x8ae7a  call     class SecurityTask Microsoft.ReportingServices.Library.AuthzData::FindTaskByID(string id)
0x8ae7f  dup
0x8ae80  callvirt instance valuetype SecurityScope SecurityTask::get_Scope()
0x8ae85  ldloc.0
0x8ae86  callvirt instance valuetype SecurityScope SecurityTask::get_Scope()
0x8ae8b  beq.s    loc_8AE93
0x8ae8d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MixedTasksException::.ctor()
0x8ae92  throw
0x8ae93  ldloc.1
0x8ae94  callvirt instance void SecurityTask::IncludeMyselfInMask(char[] mask)
0x8ae99  ldloc.2
0x8ae9a  ldc.i4.1
0x8ae9b  add
0x8ae9c  stloc.2
0x8ae9d  ldloc.2
0x8ae9e  ldarg.0
0x8ae9f  ldlen
0x8aea0  conv.i4
0x8aea1  blt.s    loc_8AE67
0x8aea3  ldarg.1
0x8aea4  ldloc.0
0x8aea5  callvirt instance valuetype SecurityScope SecurityTask::get_Scope()
0x8aeaa  stind.i4
0x8aeab  ldloc.1
0x8aeac  newobj   instance void [mscorlib]System.String::.ctor(char[])
0x8aeb1  ret
```
