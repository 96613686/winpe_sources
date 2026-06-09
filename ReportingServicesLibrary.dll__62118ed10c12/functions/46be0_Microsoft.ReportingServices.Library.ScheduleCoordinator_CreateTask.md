# Microsoft.ReportingServices.Library.ScheduleCoordinator::CreateTask

- ea: `0x46be0`
- end: `0x46cbc`
- name: `Microsoft.ReportingServices.Library.ScheduleCoordinator::CreateTask`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x3c180`

## callees

- `0x1d780`
- `0x46be0`
- `0x47510`
- `0x47b40`
- `0x71e00`

## string_xrefs

- `0x46be3`: `ScheduleDefinition`
- `0x46c82`: `Schedule Created at {0} by {1}`

## pseudocode

```c

```

## disassembly

```asm
0x46be0  ldarg.3
0x46be1  brtrue.s loc_46BEE
0x46be3  ldstr    aScheduledefini// "ScheduleDefinition"
0x46be8  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x46bed  throw
0x46bee  ldarg.0
0x46bef  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.ScheduleCoordinator::m_service
0x46bf4  ldarg.s  4
0x46bf6  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath Microsoft.ReportingServices.Library.RSService::ExternalToCatalogItemPath(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath source)
0x46bfb  stloc.0
0x46bfc  ldarg.0
0x46bfd  ldloc.0
0x46bfe  ldc.i4.s 9
0x46c00  call     instance void Microsoft.ReportingServices.Library.ScheduleCoordinator::CheckExistanceAndAccess(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath path, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CatalogOperation operation)
0x46c05  ldarg.1
0x46c06  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::.ctor(valuetype [mscorlib]System.Guid)
0x46c0b  stloc.1
0x46c0c  ldloc.1
0x46c0d  ldarg.2
0x46c0e  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::set_Name(string)
0x46c13  ldloc.1
0x46c14  ldloc.0
0x46c15  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::set_Path(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath)
0x46c1a  ldloc.1
0x46c1b  ldc.i4.1
0x46c1c  stloc.2
0x46c1d  ldloca.s 2
0x46c1f  constrained. [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.InternalEvents
0x46c25  callvirt instance string [mscorlib]System.Object::ToString()
0x46c2a  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::set_EventType(string)
0x46c2f  ldloc.1
0x46c30  ldloc.1
0x46c31  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_ID()
0x46c36  stloc.3
0x46c37  ldloca.s 3
0x46c39  constrained. [mscorlib]System.Guid
0x46c3f  callvirt instance string [mscorlib]System.Object::ToString()
0x46c44  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::set_EventData(string)
0x46c49  ldloc.1
0x46c4a  ldc.i4.0
0x46c4b  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::set_Type(valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ScheduleType)
0x46c50  ldarg.3
0x46c51  ldloc.1
0x46c52  callvirt instance void Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::PopulateTaskWithThis(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task task)
0x46c57  ldloc.1
0x46c58  ldarg.0
0x46c59  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.ScheduleCoordinator::m_userContext
0x46c5e  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::set_Creator(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext)
0x46c63  ldarg.0
0x46c64  ldfld    class Microsoft.ReportingServices.Library.SchedulingDBInterface Microsoft.ReportingServices.Library.ScheduleCoordinator::m_dbIface
0x46c69  ldloc.1
0x46c6a  callvirt instance void Microsoft.ReportingServices.Library.SchedulingDBInterface::CreateTask(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task task)
0x46c6f  ldarg.0
0x46c70  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.ScheduleCoordinator::m_tracer
0x46c75  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x46c7a  brfalse.s loc_46CA7
0x46c7c  ldarg.0
0x46c7d  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.ScheduleCoordinator::m_tracer
0x46c82  ldstr    aScheduleCreate// "Schedule Created at {0} by {1}"
0x46c87  ldc.i4.2
0x46c88  newarr   [mscorlib]System.Object
0x46c8d  dup
0x46c8e  ldc.i4.0
0x46c8f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x46c94  box      [mscorlib]System.DateTime
0x46c99  stelem.ref
0x46c9a  dup
0x46c9b  ldc.i4.1
0x46c9c  call     string [mscorlib]System.Environment::get_UserName()
0x46ca1  stelem.ref
0x46ca2  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x46ca7  ldloc.1
0x46ca8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_ID()
0x46cad  stloc.3
0x46cae  ldloca.s 3
0x46cb0  constrained. [mscorlib]System.Guid
0x46cb6  callvirt instance string [mscorlib]System.Object::ToString()
0x46cbb  ret
```
