# Microsoft.ReportingServices.Library.EnableCommentsTask::EnableCommentsOnRole

- ea: `0x59830`
- end: `0x598ea`
- name: `Microsoft.ReportingServices.Library.EnableCommentsTask::EnableCommentsOnRole`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x59750`

## callees

- `0x48e10`
- `0x49110`
- `0x59830`
- `0x598f0`
- `0x8ae30`

## string_xrefs

- `0x59851`: `No permissions updates were needed for role: {0}`
- `0x59877`: `Start of enabling of comments for role: {0}`
- `0x5989c`: `End of enabling of comments for role: {0}`
- `0x598ba`: `Error on enabling comments for role: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x59830  ldarg.2
0x59831  ldarg.1
0x59832  ldloca.s 0
0x59834  ldloca.s 1
0x59836  callvirt instance void Microsoft.ReportingServices.Library.Security::CatalogGetRoleProperties(string roleName, [out] string& roleDescription, [out] class Microsoft.ReportingServices.Library.Soap.Task[]& tasks)
0x5983b  ldarg.0
0x5983c  ldloc.1
0x5983d  call     instance string[] Microsoft.ReportingServices.Library.EnableCommentsTask::GetTaskIdsWithCommentsPermissions(class Microsoft.ReportingServices.Library.Soap.Task[] tasks)
0x59842  stloc.2
0x59843  ldloc.2
0x59844  ldlen
0x59845  conv.i4
0x59846  ldloc.1
0x59847  ldlen
0x59848  conv.i4
0x59849  bne.un.s loc_59867
0x5984b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x59850  ldc.i4.3
0x59851  ldstr    aNoPermissionsU// "No permissions updates were needed for "...
0x59856  ldc.i4.1
0x59857  newarr   [mscorlib]System.Object
0x5985c  dup
0x5985d  ldc.i4.0
0x5985e  ldarg.1
0x5985f  stelem.ref
0x59860  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x59865  ldc.i4.1
0x59866  ret
0x59867  ldloc.2
0x59868  ldloca.s 3
0x5986a  call     string TaskList::TaskListToTaskMask(string[] taskIDs, [out] valuetype SecurityScope& scope)
0x5986f  stloc.s  4
0x59871  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x59876  ldc.i4.3
0x59877  ldstr    aStartOfEnablin// "Start of enabling of comments for role:"...
0x5987c  ldc.i4.1
0x5987d  newarr   [mscorlib]System.Object
0x59882  dup
0x59883  ldc.i4.0
0x59884  ldarg.1
0x59885  stelem.ref
0x59886  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x5988b  ldarg.2
0x5988c  ldarg.1
0x5988d  ldloc.0
0x5988e  ldloc.s  4
0x59890  ldloc.3
0x59891  callvirt instance void Microsoft.ReportingServices.Library.Security::SetRolePropertiesAndInvalidatePolicies(string roleName, string roleDescription, string taskMask, valuetype SecurityScope scope)
0x59896  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x5989b  ldc.i4.3
0x5989c  ldstr    aEndOfEnablingO// "End of enabling of comments for role: {"...
0x598a1  ldc.i4.1
0x598a2  newarr   [mscorlib]System.Object
0x598a7  dup
0x598a8  ldc.i4.0
0x598a9  ldarg.1
0x598aa  stelem.ref
0x598ab  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x598b0  leave.s  loc_598E5
0x598b2  stloc.s  5
0x598b4  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x598b9  ldc.i4.1
0x598ba  ldstr    aErrorOnEnablin// "Error on enabling comments for role: {0"...
0x598bf  ldc.i4.1
0x598c0  newarr   [mscorlib]System.Object
0x598c5  dup
0x598c6  ldc.i4.0
0x598c7  ldarg.1
0x598c8  stelem.ref
0x598c9  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x598ce  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x598d3  ldc.i4.1
0x598d4  ldloc.s  5
0x598d6  callvirt instance string [mscorlib]System.Object::ToString()
0x598db  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x598e0  ldc.i4.0
0x598e1  stloc.s  6
0x598e3  leave.s  loc_598E7
0x598e5  ldc.i4.1
0x598e6  ret
0x598e7  ldloc.s  6
0x598e9  ret
```
