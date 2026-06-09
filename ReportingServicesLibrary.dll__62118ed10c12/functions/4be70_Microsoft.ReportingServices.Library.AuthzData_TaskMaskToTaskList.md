# Microsoft.ReportingServices.Library.AuthzData::TaskMaskToTaskList

- ea: `0x4be70`
- end: `0x4bed9`
- name: `Microsoft.ReportingServices.Library.AuthzData::TaskMaskToTaskList`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x48e10`

## callees

- `0x4be70`
- `0x73c80`
- `0x8aec0`

## string_xrefs

- `0x4beb4`: `Unsupported SecurityScope.`
- `0x4bec7`: `No task were found in the list.`

## pseudocode

```c

```

## disassembly

```asm
0x4be70  ldarg.1
0x4be71  switch   loc_4BE84, loc_4BE94, loc_4BEA4
0x4be82  br.s     loc_4BEB4
0x4be84  ldarg.0
0x4be85  ldsfld   class CatalogItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTasks
0x4be8a  stloc.1
0x4be8b  ldloc.1
0x4be8c  call     class TaskList TaskList::TaskMaskToTaskList(string taskMask, class SecurityTask[] allTasks)
0x4be91  stloc.0
0x4be92  br.s     loc_4BEBF
0x4be94  ldarg.0
0x4be95  ldsfld   class CatalogTask[] Microsoft.ReportingServices.Library.AuthzData::m_CatalogTasks
0x4be9a  stloc.1
0x4be9b  ldloc.1
0x4be9c  call     class TaskList TaskList::TaskMaskToTaskList(string taskMask, class SecurityTask[] allTasks)
0x4bea1  stloc.0
0x4bea2  br.s     loc_4BEBF
0x4bea4  ldarg.0
0x4bea5  ldsfld   class ModelItemTask[] Microsoft.ReportingServices.Library.AuthzData::m_ModelItemTasks
0x4beaa  stloc.1
0x4beab  ldloc.1
0x4beac  call     class TaskList TaskList::TaskMaskToTaskList(string taskMask, class SecurityTask[] allTasks)
0x4beb1  stloc.0
0x4beb2  br.s     loc_4BEBF
0x4beb4  ldstr    aUnsupportedSec// "Unsupported SecurityScope."
0x4beb9  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x4bebe  throw
0x4bebf  ldloc.0
0x4bec0  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class SecurityTask>::get_Count()
0x4bec5  brtrue.s loc_4BED2
0x4bec7  ldstr    aNoTaskWereFoun// "No task were found in the list."
0x4becc  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x4bed1  throw
0x4bed2  ldloc.0
0x4bed3  call     class Microsoft.ReportingServices.Library.Soap.Task[] Microsoft.ReportingServices.Library.Soap.Task::TaskListToThisArray(class TaskList tasks)
0x4bed8  ret
```
