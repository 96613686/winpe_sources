# System.Web.Hosting.ProcessHost::StopAppDomainProtocol

- ea: `0x16b970`
- end: `0x16ba10`
- name: `System.Web.Hosting.ProcessHost::StopAppDomainProtocol`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x29e30`
- `0x34fa0`
- `0x568c0`
- `0x15e580`
- `0x15eb90`
- `0x160530`
- `0x16b4c0`
- `0x16b970`

## string_xrefs

- `0x16b981`: `protocolId`
- `0x16b9ef`: `Failure_Stop_AppDomain_Protocol`

## pseudocode

```c

```

## disassembly

```asm
0x16b970  ldarg.1
0x16b971  brtrue.s loc_16B97E
0x16b973  ldstr    aAppid_0// "appId"
0x16b978  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x16b97d  throw
0x16b97e  ldarg.2
0x16b97f  brtrue.s loc_16B98C
0x16b981  ldstr    aProtocolid// "protocolId"
0x16b986  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x16b98b  throw
0x16b98c  ldarg.0
0x16b98d  ldarg.2
0x16b98e  call     instance class [mscorlib]System.Type System.Web.Hosting.ProcessHost::GetAppDomainProtocolHandlerType(string protocolId)
0x16b993  stloc.0
0x16b994  ldnull
0x16b995  stloc.1
0x16b996  ldarg.0
0x16b997  ldfld    class System.Web.Hosting.ApplicationManager System.Web.Hosting.ProcessHost::_appManager
0x16b99c  ldarg.1
0x16b99d  callvirt instance class System.Web.Hosting.LockableAppDomainContext System.Web.Hosting.ApplicationManager::GetLockableAppDomainContext(string appId)
0x16b9a2  stloc.2
0x16b9a3  ldloc.2
0x16b9a4  stloc.3
0x16b9a5  ldc.i4.0
0x16b9a6  stloc.s  4
0x16b9a8  ldloc.3
0x16b9a9  ldloca.s 4
0x16b9ab  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x16b9b0  ldarg.0
0x16b9b1  ldfld    class System.Web.Hosting.ApplicationManager System.Web.Hosting.ProcessHost::_appManager
0x16b9b6  ldarg.1
0x16b9b7  ldloc.0
0x16b9b8  callvirt instance class System.Web.Hosting.IRegisteredObject System.Web.Hosting.ApplicationManager::GetObject(string appId, class [mscorlib]System.Type type)
0x16b9bd  castclass System.Web.Hosting.AppDomainProtocolHandler
0x16b9c2  stloc.1
0x16b9c3  leave.s  loc_16B9D0
0x16b9c5  ldloc.s  4
0x16b9c7  brfalse.s loc_16B9CF
0x16b9c9  ldloc.3
0x16b9ca  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x16b9cf  endfinally
0x16b9d0  ldloc.1
0x16b9d1  brfalse.s loc_16B9DA
0x16b9d3  ldloc.1
0x16b9d4  ldarg.3
0x16b9d5  callvirt instance void System.Web.Hosting.AppDomainProtocolHandler::StopProtocol(bool immediate)
0x16b9da  leave.s  loc_16BA0F
0x16b9dc  stloc.s  5
0x16b9de  newobj   instance void System.Web.ProcessImpersonationContext::.ctor()
0x16b9e3  stloc.s  6
0x16b9e5  ldloc.s  5
0x16b9e7  ldc.i4.1
0x16b9e8  newarr   [mscorlib]System.String
0x16b9ed  dup
0x16b9ee  ldc.i4.0
0x16b9ef  ldstr    aFailureStopApp_0// "Failure_Stop_AppDomain_Protocol"
0x16b9f4  call     string System.Web.SR::GetString(string name)
0x16b9f9  stelem.ref
0x16b9fa  call     void System.Web.Util.Misc::ReportUnhandledException(class [mscorlib]System.Exception e, string[] strings)
0x16b9ff  leave.s  loc_16BA0D
0x16ba01  ldloc.s  6
0x16ba03  brfalse.s loc_16BA0C
0x16ba05  ldloc.s  6
0x16ba07  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16ba0c  endfinally
0x16ba0d  rethrow
0x16ba0f  ret
```
