# Microsoft.ReportingServices.Library.ServiceAppDomainController::CheckForExceedingMemoryRecycle

- ea: `0x4f040`
- end: `0x4f0da`
- name: `Microsoft.ReportingServices.Library.ServiceAppDomainController::CheckForExceedingMemoryRecycle`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x4f3b0`

## callees

- `0xf0f0`
- `0x4f040`

## string_xrefs

- `0x4f08c`: `Memory Limits Exceeded.  AppDomain Recycling will be attempted.`
- `0x4f09c`: `Memory Limits Exceeded.  AppDomain Recycling will be attempted.`

## pseudocode

```c

```

## disassembly

```asm
0x4f040  ldc.i4.4
0x4f041  call     valuetype [ReportingServicesAppDomainManager]Microsoft.ReportingServices.HostingInterfaces.RsMemoryPressureLevel Microsoft.ReportingServices.Library.Global::GetCurrentMemoryLevel()
0x4f046  bne.un   loc_4F0D2
0x4f04b  ldc.i4.s 0xA
0x4f04d  ldarg.1
0x4f04e  ldflda   int32 Recycle::memoryExceedingLimitCount
0x4f053  dup
0x4f054  ldind.i4
0x4f055  ldc.i4.1
0x4f056  add
0x4f057  stloc.0
0x4f058  ldloc.0
0x4f059  stind.i4
0x4f05a  ldloc.0
0x4f05b  bne.un.s loc_4F0D9
0x4f05d  ldarg.1
0x4f05e  ldc.i4.0
0x4f05f  stfld    int32 Recycle::memoryExceedingLimitCount
0x4f064  ldarg.1
0x4f065  ldc.i4.1
0x4f066  stfld    bool Recycle::memoryRecycle
0x4f06b  ldarg.1
0x4f06c  ldc.i4.1
0x4f06d  stfld    bool Recycle::ensureWindowsAppDomainUnload
0x4f072  ldarg.1
0x4f073  ldc.i4.1
0x4f074  stfld    bool Recycle::cycleWebAppDomains
0x4f079  ldarg.1
0x4f07a  ldc.i4.1
0x4f07b  stfld    bool Recycle::cycleWindowsServiceAppDomain
0x4f080  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f085  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x4f08a  brfalse.s loc_4F0D9
0x4f08c  ldstr    aMemoryLimitsEx// "Memory Limits Exceeded.  AppDomain Recy"...
0x4f091  call     void [mscorlib]System.Console::WriteLine(string)
0x4f096  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f09b  ldc.i4.2
0x4f09c  ldstr    aMemoryLimitsEx// "Memory Limits Exceeded.  AppDomain Recy"...
0x4f0a1  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4f0a6  ldarg.0
0x4f0a7  ldfld    class [mscorlib]System.AppDomain Microsoft.ReportingServices.Library.ServiceAppDomainController::m_workerAppDomain
0x4f0ac  brfalse.s loc_4F0D9
0x4f0ae  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x4f0b3  ldc.i4   0x8D
0x4f0b8  ldc.i4.1
0x4f0b9  newarr   [mscorlib]System.Object
0x4f0be  dup
0x4f0bf  ldc.i4.0
0x4f0c0  ldarg.0
0x4f0c1  ldfld    class [mscorlib]System.AppDomain Microsoft.ReportingServices.Library.ServiceAppDomainController::m_workerAppDomain
0x4f0c6  callvirt instance string [mscorlib]System.AppDomain::get_FriendlyName()
0x4f0cb  stelem.ref
0x4f0cc  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteInformation(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Event, object[])
0x4f0d1  ret
0x4f0d2  ldarg.1
0x4f0d3  ldc.i4.0
0x4f0d4  stfld    int32 Recycle::memoryExceedingLimitCount
0x4f0d9  ret
```
