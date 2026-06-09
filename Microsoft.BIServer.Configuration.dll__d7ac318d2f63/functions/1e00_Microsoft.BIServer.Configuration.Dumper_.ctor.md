# Microsoft.BIServer.Configuration.Dumper::.ctor

- ea: `0x1e00`
- end: `0x1eb5`
- name: `Microsoft.BIServer.Configuration.Dumper::.ctor`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1ec0`

## callees

- `0xc90`
- `0x22b0`
- `0x2330`

## string_xrefs

- `0x1e2d`: `Dumper.path`

## pseudocode

```c

```

## disassembly

```asm
0x1e00  ldarg.0
0x1e01  call     instance void [mscorlib]System.Object::.ctor()
0x1e06  ldarg.0
0x1e07  ldarg.2
0x1e08  stfld    class Microsoft.BIServer.Configuration.IDumperAdapter Microsoft.BIServer.Configuration.Dumper::_dumperAdapter
0x1e0d  ldarg.2
0x1e0e  callvirt instance void Microsoft.BIServer.Configuration.IDumperAdapter::Prepare()
0x1e13  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x1e18  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x1e1d  stloc.1
0x1e1e  ldloca.s 1
0x1e20  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e25  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1e2a  pop
0x1e2b  ldarg.0
0x1e2c  ldarg.1
0x1e2d  ldstr    aDumperPath// "Dumper.path"
0x1e32  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Get(string)
0x1e37  stfld    string Microsoft.BIServer.Configuration.Dumper::_dumpLocation
0x1e3c  ldarg.0
0x1e3d  ldarg.1
0x1e3e  ldstr    aName// "Name"
0x1e43  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Get(string)
0x1e48  stfld    string Microsoft.BIServer.Configuration.Dumper::_serviceName
0x1e4d  ldarg.0
0x1e4e  ldarg.1
0x1e4f  ldstr    aDumperFlags// "Dumper.flags"
0x1e54  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Get(string)
0x1e59  call     valuetype Microsoft.BIServer.Configuration.DumperFlags Microsoft.BIServer.Configuration.Dumper::ParseFlags(string flags)
0x1e5e  stfld    valuetype Microsoft.BIServer.Configuration.DumperFlags Microsoft.BIServer.Configuration.Dumper::_dumperFlags
0x1e63  ldarg.1
0x1e64  ldstr    aDumperPreventi// "Dumper.preventIfContains"
0x1e69  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Get(string)
0x1e6e  stloc.0
0x1e6f  ldarg.0
0x1e70  ldloc.0
0x1e71  call     class [System]System.Collections.Generic.ISet`1<string> Microsoft.BIServer.Configuration.Dumper::ParseList(string list)
0x1e76  stfld    class [System]System.Collections.Generic.ISet`1<string> Microsoft.BIServer.Configuration.Dumper::_errorsExcluded
0x1e7b  ldstr    aDoNotDumpOn0// "Do not dump on: {0}"
0x1e80  ldc.i4.1
0x1e81  newarr   [mscorlib]System.Object
0x1e86  dup
0x1e87  ldc.i4.0
0x1e88  ldloc.0
0x1e89  stelem.ref
0x1e8a  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x1e8f  ldstr    aSettingUnhandl// "Setting unhandled exception handler"
0x1e94  call     T0x2B000015
0x1e99  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Trace(string, object[])
0x1e9e  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x1ea3  ldarg.0
0x1ea4  ldftn    instance void Microsoft.BIServer.Configuration.Dumper::DefaultExceptionHandler(object sender, class [mscorlib]System.UnhandledExceptionEventArgs args)
0x1eaa  newobj   instance void [mscorlib]System.UnhandledExceptionEventHandler::.ctor(object, native int)
0x1eaf  callvirt instance void [mscorlib]System.AppDomain::add_UnhandledException(class [mscorlib]System.UnhandledExceptionEventHandler)
0x1eb4  ret
```
