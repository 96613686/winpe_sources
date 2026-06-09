# Microsoft.BIServer.BIService.Program::Main

- ea: `0x23e0`
- end: `0x242c`
- name: `Microsoft.BIServer.BIService.Program::Main`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0xa60`
- `0x1510`
- `0x1520`
- `0x23e0`
- `0x2430`

## pseudocode

```c

```

## disassembly

```asm
0x23e0  .entrypoint
0x23e5  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Args::PauseIfDebugSwitch()
0x23ea  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x23ef  callvirt instance string [mscorlib]System.AppDomain::get_BaseDirectory()
0x23f4  call     void [mscorlib]System.IO.Directory::SetCurrentDirectory(string)
0x23f9  call     class [mscorlib]System.IDisposable Microsoft.BIServer.BIService.Program::CreateLogger()
0x23fe  stloc.0
0x23ff  newobj   instance void Microsoft.BIServer.BIService.BIService::.ctor()
0x2404  stloc.1
0x2405  call     bool [mscorlib]System.Environment::get_UserInteractive()
0x240a  brfalse.s loc_2419
0x240c  ldloc.1
0x240d  newobj   instance void Microsoft.BIServer.BIService.ConsoleDriver::.ctor(class Microsoft.BIServer.BIService.BIService service)
0x2412  callvirt instance void Microsoft.BIServer.BIService.ConsoleDriver::Start()
0x2417  leave.s  loc_242B
0x2419  ldloc.1
0x241a  call     void [System.ServiceProcess]System.ServiceProcess.ServiceBase::Run(class [System.ServiceProcess]System.ServiceProcess.ServiceBase)
0x241f  leave.s  loc_242B
0x2421  ldloc.0
0x2422  brfalse.s loc_242A
0x2424  ldloc.0
0x2425  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x242a  endfinally
0x242b  ret
```
