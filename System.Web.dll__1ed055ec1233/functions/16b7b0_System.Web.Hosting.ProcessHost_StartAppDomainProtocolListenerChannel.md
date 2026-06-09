# System.Web.Hosting.ProcessHost::StartAppDomainProtocolListenerChannel

- ea: `0x16b7b0`
- end: `0x16b8b8`
- name: `System.Web.Hosting.ProcessHost::StartAppDomainProtocolListenerChannel`
- size: `264`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x18990`
- `0x29e30`
- `0x34fa0`
- `0x568c0`
- `0x15ea20`
- `0x160530`
- `0x160900`
- `0x1609d0`
- `0x1664c0`
- `0x16b4c0`
- `0x16b7b0`
- `0x16bdb0`
- `0x16bee0`
- `0x16c210`

## string_xrefs

- `0x16b7c1`: `protocolId`
- `0x16b864`: `Failure_Create_Listener_Shim`

## pseudocode

```c

```

## disassembly

```asm
0x16b7b0  ldarg.1
0x16b7b1  brtrue.s loc_16B7BE
0x16b7b3  ldstr    aAppid_0// "appId"
0x16b7b8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x16b7bd  throw
0x16b7be  ldarg.2
0x16b7bf  brtrue.s loc_16B7CC
0x16b7c1  ldstr    aProtocolid// "protocolId"
0x16b7c6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x16b7cb  throw
0x16b7cc  ldarg.0
0x16b7cd  ldarg.1
0x16b7ce  ldnull
0x16b7cf  call     instance class System.Web.Hosting.ISAPIApplicationHost System.Web.Hosting.ProcessHost::CreateAppHost(string appId, string appPath)
0x16b7d4  stloc.0
0x16b7d5  ldarg.0
0x16b7d6  ldarg.2
0x16b7d7  call     instance class [mscorlib]System.Type System.Web.Hosting.ProcessHost::GetAppDomainProtocolHandlerType(string protocolId)
0x16b7dc  stloc.1
0x16b7dd  ldnull
0x16b7de  stloc.2
0x16b7df  ldarg.0
0x16b7e0  ldfld    class System.Web.Hosting.ApplicationManager System.Web.Hosting.ProcessHost::_appManager
0x16b7e5  ldarg.1
0x16b7e6  callvirt instance class System.Web.Hosting.LockableAppDomainContext System.Web.Hosting.ApplicationManager::GetLockableAppDomainContext(string appId)
0x16b7eb  stloc.3
0x16b7ec  ldloc.3
0x16b7ed  stloc.s  4
0x16b7ef  ldc.i4.0
0x16b7f0  stloc.s  5
0x16b7f2  ldloc.s  4
0x16b7f4  ldloca.s 5
0x16b7f6  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x16b7fb  newobj   instance void System.Web.Hosting.HostingEnvironmentParameters::.ctor()
0x16b800  stloc.s  6
0x16b802  ldloc.s  6
0x16b804  ldc.i4.2
0x16b805  callvirt instance void System.Web.Hosting.HostingEnvironmentParameters::set_HostingFlags(valuetype System.Web.Hosting.HostingEnvironmentFlags value)
0x16b80a  ldarg.0
0x16b80b  ldarg.1
0x16b80c  ldloc.0
0x16b80d  ldloc.s  6
0x16b80f  ldloc.3
0x16b810  call     instance void System.Web.Hosting.ProcessHost::PreloadApplicationIfRequired(string appId, class System.Web.Hosting.IApplicationHost appHostParameter, class System.Web.Hosting.HostingEnvironmentParameters hostingParameters, class System.Web.Hosting.LockableAppDomainContext ac)
0x16b815  ldarg.0
0x16b816  ldfld    class System.Web.Hosting.ApplicationManager System.Web.Hosting.ProcessHost::_appManager
0x16b81b  ldarg.1
0x16b81c  ldloc.1
0x16b81d  ldloc.0
0x16b81e  ldc.i4.0
0x16b81f  ldloc.s  6
0x16b821  callvirt instance class System.Web.Hosting.IRegisteredObject System.Web.Hosting.ApplicationManager::CreateObjectInternal(string appId, class [mscorlib]System.Type type, class System.Web.Hosting.IApplicationHost appHost, bool failIfExists, class System.Web.Hosting.HostingEnvironmentParameters hostingParameters)
0x16b826  castclass System.Web.Hosting.AppDomainProtocolHandler
0x16b82b  stloc.2
0x16b82c  ldarg.0
0x16b82d  ldfld    class System.Web.Hosting.ApplicationManager System.Web.Hosting.ProcessHost::_appManager
0x16b832  ldarg.1
0x16b833  ldtoken  System.Web.Hosting.ListenerAdapterDispatchShim
0x16b838  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16b83d  ldloc.0
0x16b83e  ldc.i4.0
0x16b83f  ldloc.s  6
0x16b841  callvirt instance class System.Web.Hosting.IRegisteredObject System.Web.Hosting.ApplicationManager::CreateObjectInternal(string appId, class [mscorlib]System.Type type, class System.Web.Hosting.IApplicationHost appHost, bool failIfExists, class System.Web.Hosting.HostingEnvironmentParameters hostingParameters)
0x16b846  castclass System.Web.Hosting.ListenerAdapterDispatchShim
0x16b84b  stloc.s  7
0x16b84d  ldloc.s  7
0x16b84f  brfalse.s loc_16B864
0x16b851  ldloc.s  7
0x16b853  ldloc.2
0x16b854  ldarg.3
0x16b855  callvirt instance void System.Web.Hosting.ListenerAdapterDispatchShim::StartListenerChannel(class System.Web.Hosting.AppDomainProtocolHandler handler, class System.Web.Hosting.IListenerChannelCallback listenerCallback)
0x16b85a  ldloc.s  7
0x16b85c  ldc.i4.1
0x16b85d  callvirt instance void System.Web.Hosting.IRegisteredObject::Stop(bool immediate)
0x16b862  br.s     loc_16B874
0x16b864  ldstr    aFailureCreateL// "Failure_Create_Listener_Shim"
0x16b869  call     string System.Web.SR::GetString(string name)
0x16b86e  newobj   instance void System.Web.HttpException::.ctor(string message)
0x16b873  throw
0x16b874  leave.s  loc_16B882
0x16b876  ldloc.s  5
0x16b878  brfalse.s loc_16B881
0x16b87a  ldloc.s  4
0x16b87c  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x16b881  endfinally
0x16b882  leave.s  loc_16B8B7
0x16b884  stloc.s  8
0x16b886  newobj   instance void System.Web.ProcessImpersonationContext::.ctor()
0x16b88b  stloc.s  9
0x16b88d  ldloc.s  8
0x16b88f  ldc.i4.1
0x16b890  newarr   [mscorlib]System.String
0x16b895  dup
0x16b896  ldc.i4.0
0x16b897  ldstr    aFailureStartAp// "Failure_Start_AppDomain_Listener"
0x16b89c  call     string System.Web.SR::GetString(string name)
0x16b8a1  stelem.ref
0x16b8a2  call     void System.Web.Util.Misc::ReportUnhandledException(class [mscorlib]System.Exception e, string[] strings)
0x16b8a7  leave.s  loc_16B8B5
0x16b8a9  ldloc.s  9
0x16b8ab  brfalse.s loc_16B8B4
0x16b8ad  ldloc.s  9
0x16b8af  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16b8b4  endfinally
0x16b8b5  rethrow
0x16b8b7  ret
```
