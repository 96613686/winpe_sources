# Microsoft.BIServer.BIService.BIService::UpdateConfigsAndRestartProcesses

- ea: `0xce0`
- end: `0xd61`
- name: `Microsoft.BIServer.BIService.BIService::UpdateConfigsAndRestartProcesses`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x3110`

## callees

- `0xce0`
- `0xfd0`
- `0x1a50`
- `0x1a60`
- `0x1bd0`
- `0x21a0`

## pseudocode

```c

```

## disassembly

```asm
0xce0  ldarg.1
0xce1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0xce6  stloc.0
0xce7  br.s     loc_D4C
0xce9  ldloc.0
0xcea  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0xcef  stloc.1
0xcf0  ldstr    aRestartingProc// "Restarting process: {0}"
0xcf5  ldc.i4.1
0xcf6  newarr   [mscorlib]System.Object
0xcfb  dup
0xcfc  ldc.i4.0
0xcfd  ldloc.1
0xcfe  stelem.ref
0xcff  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0xd04  ldloc.1
0xd05  ldarg.2
0xd06  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.BIService::GetProcessConfigForProcess(string processName, class Microsoft.BIServer.BIService.ServiceConfig serviceConfig)
0xd0b  stloc.2
0xd0c  ldarg.0
0xd0d  ldfld    class Microsoft.BIServer.BIService.ManagedProcesses Microsoft.BIServer.BIService.BIService::_managedProcesses
0xd12  ldloc.1
0xd13  callvirt instance class Microsoft.BIServer.BIService.ManagedProcess Microsoft.BIServer.BIService.ManagedProcesses::GetManagedProcessByName(string procName)
0xd18  callvirt instance class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::get_ProcessConfig()
0xd1d  ldloc.2
0xd1e  callvirt instance void Microsoft.BIServer.BIService.ProcessConfig::set_Config(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> value)
0xd23  ldarg.0
0xd24  ldfld    class Microsoft.BIServer.BIService.ManagedProcesses Microsoft.BIServer.BIService.BIService::_managedProcesses
0xd29  ldloc.1
0xd2a  callvirt instance void Microsoft.BIServer.BIService.ManagedProcesses::RestartProcessByName(string procName)
0xd2f  leave.s  loc_D4C
0xd31  stloc.3
0xd32  ldstr    aExceptionWhenR// "Exception when restarting process named"...
0xd37  ldc.i4.2
0xd38  newarr   [mscorlib]System.Object
0xd3d  dup
0xd3e  ldc.i4.0
0xd3f  ldloc.1
0xd40  stelem.ref
0xd41  dup
0xd42  ldc.i4.1
0xd43  ldloc.3
0xd44  stelem.ref
0xd45  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0xd4a  leave.s  loc_D4C
0xd4c  ldloc.0
0xd4d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd52  brtrue.s loc_CE9
0xd54  leave.s  loc_D60
0xd56  ldloc.0
0xd57  brfalse.s loc_D5F
0xd59  ldloc.0
0xd5a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd5f  endfinally
0xd60  ret
```
