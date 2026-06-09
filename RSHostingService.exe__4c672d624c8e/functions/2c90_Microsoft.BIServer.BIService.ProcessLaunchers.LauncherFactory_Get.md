# Microsoft.BIServer.BIService.ProcessLaunchers.LauncherFactory::Get

- ea: `0x2c90`
- end: `0x2cf2`
- name: `Microsoft.BIServer.BIService.ProcessLaunchers.LauncherFactory::Get`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1bf0`
- `0x1c00`

## callees

- `0x2170`
- `0x2180`
- `0x2860`
- `0x2af0`
- `0x2c90`

## string_xrefs

- `0x2cae`: `AnalysisServices`

## pseudocode

```c

```

## disassembly

```asm
0x2c90  ldarg.0
0x2c91  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Launcher()
0x2c96  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2c9b  brfalse.s loc_2CA8
0x2c9d  ldarg.0
0x2c9e  ldstr    aDefault// "Default"
0x2ca3  callvirt instance void Microsoft.BIServer.BIService.ProcessConfig::set_Launcher(string value)
0x2ca8  ldarg.0
0x2ca9  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Launcher()
0x2cae  ldstr    aAnalysisservic// "AnalysisServices"
0x2cb3  ldc.i4.3
0x2cb4  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2cb9  brfalse.s loc_2CC2
0x2cbb  ldarg.0
0x2cbc  newobj   instance void Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::.ctor(class Microsoft.BIServer.BIService.ProcessConfig processConfig)
0x2cc1  ret
0x2cc2  ldarg.0
0x2cc3  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Launcher()
0x2cc8  ldstr    aDefault// "Default"
0x2ccd  ldc.i4.3
0x2cce  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2cd3  brfalse.s loc_2CDC
0x2cd5  ldarg.0
0x2cd6  newobj   instance void Microsoft.BIServer.BIService.ProcessLaunchers.DefaultProcessLauncher::.ctor(class Microsoft.BIServer.BIService.ProcessConfig processConfig)
0x2cdb  ret
0x2cdc  ldstr    aUnrecogonizedL// "Unrecogonized launcher: {0}"
0x2ce1  ldarg.0
0x2ce2  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Launcher()
0x2ce7  call     string [mscorlib]System.String::Format(string, object)
0x2cec  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2cf1  throw
```
