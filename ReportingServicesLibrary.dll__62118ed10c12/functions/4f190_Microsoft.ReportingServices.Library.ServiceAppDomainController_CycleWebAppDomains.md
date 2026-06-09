# Microsoft.ReportingServices.Library.ServiceAppDomainController::CycleWebAppDomains

- ea: `0x4f190`
- end: `0x4f237`
- name: `Microsoft.ReportingServices.Library.ServiceAppDomainController::CycleWebAppDomains`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x4f3b0`

## callees

- `0xf050`
- `0xf0d0`
- `0x4e7b0`
- `0x4f190`
- `0x4fb50`

## string_xrefs

- `0x4f1b1`: `Recycling ASP.NET AppDomains with memory recycling, i.e. let the current AppDomains unload before the new ones are created.`
- `0x4f200`: `Recycling ASP.NET AppDomains without memory recycling, i.e. create the new ones before the current ones fully unload.`

## pseudocode

```c

```

## disassembly

```asm
0x4f190  ldc.i4.2
0x4f191  call     class [mscorlib]System.AppDomain Microsoft.ReportingServices.Library.Global::GetAppDomain(valuetype [ReportingServicesAppDomainManager]Microsoft.ReportingServices.HostingInterfaces.RsAppDomainType appDomainType)
0x4f196  stloc.0
0x4f197  ldarg.1
0x4f198  ldfld    bool Recycle::memoryRecycle
0x4f19d  brfalse.s loc_4F1EE
0x4f19f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f1a4  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4f1a9  brfalse.s loc_4F1BB
0x4f1ab  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f1b0  ldc.i4.3
0x4f1b1  ldstr    aRecyclingAspNe// "Recycling ASP.NET AppDomains with memor"...
0x4f1b6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4f1bb  ldarg.0
0x4f1bc  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::StopHttpEndpoints()
0x4f1c1  ldloc.0
0x4f1c2  brfalse.s loc_4F1E7
0x4f1c4  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f1c9  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4f1ce  brfalse.s loc_4F1E0
0x4f1d0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f1d5  ldc.i4.3
0x4f1d6  ldstr    aRecyclingTheRe// "Recycling the ReportServer AppDomain"
0x4f1db  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4f1e0  ldloc.0
0x4f1e1  ldc.i4.1
0x4f1e2  call     void Microsoft.ReportingServices.Library.Global::UnloadAppDomain(class [mscorlib]System.AppDomain appDomain, bool memoryRecycle)
0x4f1e7  ldarg.0
0x4f1e8  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::ApplyNativeConfiguration()
0x4f1ed  ret
0x4f1ee  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f1f3  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4f1f8  brfalse.s loc_4F20A
0x4f1fa  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f1ff  ldc.i4.3
0x4f200  ldstr    aRecyclingAspNe_0// "Recycling ASP.NET AppDomains without me"...
0x4f205  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4f20a  ldarg.0
0x4f20b  call     instance void Microsoft.ReportingServices.Library.ServiceAppDomainController::ApplyNativeConfiguration()
0x4f210  ldloc.0
0x4f211  brfalse.s loc_4F236
0x4f213  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f218  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4f21d  brfalse.s loc_4F22F
0x4f21f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ServiceControllerTracer()
0x4f224  ldc.i4.3
0x4f225  ldstr    aRecyclingTheRe// "Recycling the ReportServer AppDomain"
0x4f22a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4f22f  ldloc.0
0x4f230  ldc.i4.0
0x4f231  call     void Microsoft.ReportingServices.Library.Global::UnloadAppDomain(class [mscorlib]System.AppDomain appDomain, bool memoryRecycle)
0x4f236  ret
```
