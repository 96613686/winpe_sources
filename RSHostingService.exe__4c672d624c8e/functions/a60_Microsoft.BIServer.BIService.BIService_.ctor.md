# Microsoft.BIServer.BIService.BIService::.ctor

- ea: `0xa60`
- end: `0xafb`
- name: `Microsoft.BIServer.BIService.BIService::.ctor`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x23e0`

## callees

- `0xb10`
- `0x1410`
- `0x17e0`

## string_xrefs

- `0xa94`: `Current Directory : {0}`
- `0xab1`: `configFile`
- `0xabb`: `config.json`

## pseudocode

```c

```

## disassembly

```asm
0xa60  ldarg.0
0xa61  newobj   instance void Microsoft.BIServer.BIService.ManagedProcesses::.ctor()
0xa66  stfld    class Microsoft.BIServer.BIService.ManagedProcesses Microsoft.BIServer.BIService.BIService::_managedProcesses
0xa6b  ldarg.0
0xa6c  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::.ctor()
0xa71  ldarg.0
0xa72  call     instance void Microsoft.BIServer.BIService.BIService::InitializeComponent()
0xa77  ldarg.0
0xa78  ldnull
0xa79  stfld    class Microsoft.BIServer.BIService.ManagedProcess Microsoft.BIServer.BIService.BIService::_managementProcess
0xa7e  ldarg.0
0xa7f  ldnull
0xa80  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState Microsoft.BIServer.BIService.BIService::_mgmtState
0xa85  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0xa8a  callvirt instance string [mscorlib]System.AppDomain::get_BaseDirectory()
0xa8f  call     void [mscorlib]System.Environment::set_CurrentDirectory(string)
0xa94  ldstr    aCurrentDirecto// "Current Directory : {0}"
0xa99  ldc.i4.1
0xa9a  newarr   [mscorlib]System.Object
0xa9f  dup
0xaa0  ldc.i4.0
0xaa1  call     string [mscorlib]System.Environment::get_CurrentDirectory()
0xaa6  stelem.ref
0xaa7  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0xaac  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Args [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Args::CommandLine
0xab1  ldstr    aConfigfile// "configFile"
0xab6  call     string [mscorlib]System.Environment::get_CurrentDirectory()
0xabb  ldstr    aConfigJson// "config.json"
0xac0  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xac5  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Args::GetSwitchOrDefault(string, string)
0xaca  stloc.0
0xacb  ldarg.0
0xacc  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.BIService.BIService::WebApiBackoffMaxWait
0xad1  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.BIService.BIService::WebApiBackoffExpire
0xad6  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.BIService.BIService::WebApiBackoffInitialWait
0xadb  ldsfld   int32 Microsoft.BIServer.BIService.BIService::WebApiBackoffMultiplier
0xae0  conv.r8
0xae1  newobj   instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ExponentialBackoff::.ctor(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan, float64)
0xae6  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ExponentialBackoff Microsoft.BIServer.BIService.BIService::_managementBackoff
0xaeb  ldarg.0
0xaec  ldnull
0xaed  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.TrustedWebApiProxy`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> Microsoft.BIServer.BIService.BIService::_managementStateAccessor
0xaf2  ldarg.0
0xaf3  ldloc.0
0xaf4  call     instance bool Microsoft.BIServer.BIService.BIService::SetNewConfigFilePathIfExists(string configFilePath)
0xaf9  pop
0xafa  ret
```
