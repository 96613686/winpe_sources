# Microsoft.BIServer.Configuration.Dumper::GenerateDump

- ea: `0x1f90`
- end: `0x20a2`
- name: `Microsoft.BIServer.Configuration.Dumper::GenerateDump`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1f20`
- `0x1f70`

## callees

- `0xca0`
- `0xcd0`
- `0xcf0`
- `0xd10`
- `0xd20`
- `0xd30`
- `0xd50`
- `0xd70`
- `0xd90`
- `0xdb0`
- `0xdc0`
- `0xe40`
- `0xf10`
- `0x1f90`
- `0x20b0`
- `0x2140`
- `0x21e0`
- `0x7120`
- `0x7140`

## pseudocode

```c

```

## disassembly

```asm
0x1f90  newobj   instance void RecursionGuard::.ctor()
0x1f95  stloc.0
0x1f96  ldloc.0
0x1f97  callvirt instance bool RecursionGuard::get_InRecursion()
0x1f9c  brfalse.s loc_1FA3
0x1f9e  leave    loc_20A1
0x1fa3  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ImpersonationContext::EnterServiceAccountContext()
0x1fa8  stloc.1
0x1fa9  ldarg.2
0x1faa  brfalse.s loc_1FB6
0x1fac  ldarg.1
0x1fad  brfalse.s loc_1FB6
0x1faf  ldarg.1
0x1fb0  ldarg.2
0x1fb1  call     void Microsoft.BIServer.Configuration.Dumper::LogUnhandledException(class [mscorlib]System.Exception optionalException, bool unhandledException)
0x1fb6  ldarg.0
0x1fb7  ldarg.1
0x1fb8  call     instance bool Microsoft.BIServer.Configuration.Dumper::ShouldDump(class [mscorlib]System.Exception optionalException)
0x1fbd  brtrue.s loc_1FC4
0x1fbf  leave    loc_20A1
0x1fc4  newobj   instance void Microsoft.BIServer.Configuration.DumpInstructions::.ctor()
0x1fc9  dup
0x1fca  ldarg.0
0x1fcb  ldfld    string Microsoft.BIServer.Configuration.Dumper::_dumpLocation
0x1fd0  callvirt instance void Microsoft.BIServer.Configuration.DumpInstructions::set_Location(string value)
0x1fd5  dup
0x1fd6  ldarg.0
0x1fd7  ldfld    valuetype Microsoft.BIServer.Configuration.DumperFlags Microsoft.BIServer.Configuration.Dumper::_dumperFlags
0x1fdc  callvirt instance void Microsoft.BIServer.Configuration.DumpInstructions::set_Flags(valuetype Microsoft.BIServer.Configuration.DumperFlags value)
0x1fe1  dup
0x1fe2  call     class Microsoft.BIServer.Configuration.ConfigReader Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x1fe7  callvirt instance string Microsoft.BIServer.Configuration.ConfigReader::get_InstanceId()
0x1fec  callvirt instance void Microsoft.BIServer.Configuration.DumpInstructions::set_InstanceName(string value)
0x1ff1  dup
0x1ff2  ldarg.0
0x1ff3  ldfld    string Microsoft.BIServer.Configuration.Dumper::_serviceName
0x1ff8  callvirt instance void Microsoft.BIServer.Configuration.DumpInstructions::set_ServiceName(string value)
0x1ffd  dup
0x1ffe  ldc.i4.s 0x10
0x2000  callvirt instance void Microsoft.BIServer.Configuration.DumpInstructions::set_FramesToInclude(int32 value)
0x2005  stloc.2
0x2006  ldloca.s 3
0x2008  call     bool [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::TryGetFileTargetName(string&)
0x200d  brfalse.s loc_2021
0x200f  ldloc.2
0x2010  ldloc.3
0x2011  callvirt instance void Microsoft.BIServer.Configuration.DumpInstructions::set_LogFileToInclude(string value)
0x2016  ldloc.2
0x2017  ldc.i4   0x80000
0x201c  callvirt instance void Microsoft.BIServer.Configuration.DumpInstructions::set_SizeOfLogFileToInclude(int32 value)
0x2021  ldarg.1
0x2022  brfalse.s loc_2030
0x2024  ldloc.2
0x2025  ldarg.1
0x2026  call     string Microsoft.BIServer.Configuration.Dumper::CreateDumperErrorText(class [mscorlib]System.Exception optionalException)
0x202b  callvirt instance void Microsoft.BIServer.Configuration.DumpInstructions::set_ErrorText(string value)
0x2030  nop
0x2031  ldstr    aReportServerDu// "Report server dump occurred: {0}"
0x2036  ldc.i4.1
0x2037  newarr   [mscorlib]System.Object
0x203c  dup
0x203d  ldc.i4.0
0x203e  ldloc.2
0x203f  callvirt instance string Microsoft.BIServer.Configuration.DumpInstructions::get_ErrorText()
0x2044  stelem.ref
0x2045  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0x204a  ldarg.0
0x204b  ldfld    class Microsoft.BIServer.Configuration.IDumperAdapter Microsoft.BIServer.Configuration.Dumper::_dumperAdapter
0x2050  ldloc.2
0x2051  callvirt instance string Microsoft.BIServer.Configuration.IDumperAdapter::Dump(class Microsoft.BIServer.Configuration.DumpInstructions instructions)
0x2056  stloc.s  4
0x2058  ldstr    aDumpResult0// "Dump result: {0}."
0x205d  ldc.i4.1
0x205e  newarr   [mscorlib]System.Object
0x2063  dup
0x2064  ldc.i4.0
0x2065  ldloc.s  4
0x2067  stelem.ref
0x2068  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x206d  leave.s  loc_20A1
0x206f  stloc.s  5
0x2071  ldstr    aFailedToGenera_0// "Failed to generate a dump. Error: {0}."
0x2076  ldc.i4.1
0x2077  newarr   [mscorlib]System.Object
0x207c  dup
0x207d  ldc.i4.0
0x207e  ldloc.s  5
0x2080  callvirt instance string [mscorlib]System.Object::ToString()
0x2085  stelem.ref
0x2086  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0x208b  leave.s  loc_20A1
0x208d  ldloc.1
0x208e  brfalse.s loc_2096
0x2090  ldloc.1
0x2091  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2096  endfinally
0x2097  ldloc.0
0x2098  brfalse.s loc_20A0
0x209a  ldloc.0
0x209b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20a0  endfinally
0x20a1  ret
```
