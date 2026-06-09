# Microsoft.ReportingServices.Diagnostics.Globals::InitConfiguration

- ea: `0xa850`
- end: `0xa894`
- name: `Microsoft.ReportingServices.Diagnostics.Globals::InitConfiguration`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xa8a0`

## callees

- `0x100`
- `0x6ef0`
- `0xa850`
- `0xa930`
- `0xa940`
- `0xa970`
- `0xa990`

## pseudocode

```c

```

## disassembly

```asm
0xa850  ldsfld   object Microsoft.ReportingServices.Diagnostics.Globals::StaticLock
0xa855  stloc.0
0xa856  ldc.i4.0
0xa857  stloc.1
0xa858  ldloc.0
0xa859  ldloca.s 1
0xa85b  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xa860  ldarg.1
0xa861  call     void Microsoft.ReportingServices.Diagnostics.Globals::set_CurrentApplication(valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication value)
0xa866  ldarg.0
0xa867  call     void Microsoft.ReportingServices.Diagnostics.Globals::set_ConfigurationManager(class Microsoft.ReportingServices.Diagnostics.RSConfigurationManager value)
0xa86c  ldarg.0
0xa86d  callvirt instance class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.RSConfigurationManager::GetConfiguration()
0xa872  call     void Microsoft.ReportingServices.Diagnostics.Globals::set_Configuration(class Microsoft.ReportingServices.Diagnostics.RSConfiguration value)
0xa877  call     class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0xa87c  ldarg.1
0xa87d  newobj   instance void Microsoft.ReportingServices.OnPrem.OnPremProcessingRenderingConfiguration::.ctor(class Microsoft.ReportingServices.Diagnostics.RSConfiguration configToWrap, valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication runningApplication)
0xa882  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ProcessingContext::set_Configuration(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration)
0xa887  leave.s  loc_A893
0xa889  ldloc.1
0xa88a  brfalse.s loc_A892
0xa88c  ldloc.0
0xa88d  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xa892  endfinally
0xa893  ret
```
