# Microsoft.BIServer.BIService.BIService::GetProcessConfigForProcess

- ea: `0xfd0`
- end: `0x1001`
- name: `Microsoft.BIServer.BIService.BIService::GetProcessConfigForProcess`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xce0`

## callees

- `0xfd0`
- `0x2190`
- `0x2320`
- `0x3280`

## pseudocode

```c

```

## disassembly

```asm
0xfd0  newobj   instance void <>c__DisplayClass41_0::.ctor()
0xfd5  stloc.0
0xfd6  ldloc.0
0xfd7  ldarg.0
0xfd8  stfld    string <>c__DisplayClass41_0::processName
0xfdd  ldarg.1
0xfde  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.BIServer.BIService.ProcessConfig> Microsoft.BIServer.BIService.ServiceConfig::get_ManagedProcesses()
0xfe3  ldloc.0
0xfe4  ldftn    instance bool <>c__DisplayClass41_0::<GetProcessConfigForProcess>b__0(class Microsoft.BIServer.BIService.ProcessConfig p)
0xfea  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.BIServer.BIService.ProcessConfig, bool>::.ctor(object, native int)
0xfef  call     T0x2B00000A
0xff4  stloc.1
0xff5  ldloc.1
0xff6  brfalse.s loc_FFF
0xff8  ldloc.1
0xff9  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0xffe  ret
0xfff  ldnull
0x1000  ret
```
