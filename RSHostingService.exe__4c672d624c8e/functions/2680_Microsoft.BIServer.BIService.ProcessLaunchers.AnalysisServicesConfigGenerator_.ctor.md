# Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::.ctor

- ea: `0x2680`
- end: `0x26b8`
- name: `Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::.ctor`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2aa0`

## pseudocode

```c

```

## disassembly

```asm
0x2680  ldarg.0
0x2681  call     instance void [mscorlib]System.Object::.ctor()
0x2686  ldarg.0
0x2687  ldarg.1
0x2688  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XText::.ctor(string)
0x268d  callvirt instance string [mscorlib]System.Object::ToString()
0x2692  stfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::_safeWorkspacePath
0x2697  ldarg.0
0x2698  ldarg.2
0x2699  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XText::.ctor(string)
0x269e  callvirt instance string [mscorlib]System.Object::ToString()
0x26a3  stfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::_safeLogPath
0x26a8  ldarg.0
0x26a9  ldarg.3
0x26aa  stfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::_flightRecorderTraceDefinitionPath
0x26af  ldarg.0
0x26b0  ldarg.s  4
0x26b2  stfld    int32 Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::_asPort
0x26b7  ret
```
