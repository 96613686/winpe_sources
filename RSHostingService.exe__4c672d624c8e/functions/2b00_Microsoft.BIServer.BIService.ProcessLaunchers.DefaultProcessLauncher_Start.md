# Microsoft.BIServer.BIService.ProcessLaunchers.DefaultProcessLauncher::Start

- ea: `0x2b00`
- end: `0x2c60`
- name: `Microsoft.BIServer.BIService.ProcessLaunchers.DefaultProcessLauncher::Start`
- size: `352`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1a90`
- `0x1ac0`
- `0x20d0`
- `0x20f0`
- `0x2110`
- `0x2190`
- `0x2b00`

## string_xrefs

- `0x2c1c`: `Process not started (may already be running): {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2b00  ldstr    aLaunchingProce// "Launching Process : "
0x2b05  ldarg.0
0x2b06  ldfld    class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ProcessLaunchers.DefaultProcessLauncher::_processConfig
0x2b0b  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Name()
0x2b10  call     string [mscorlib]System.String::Concat(string, string)
0x2b15  call     T0x2B000001
0x2b1a  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x2b1f  newobj   instance void [System]System.Diagnostics.Process::.ctor()
0x2b24  stloc.0
0x2b25  ldloc.0
0x2b26  ldc.i4.1
0x2b27  callvirt instance void [System]System.Diagnostics.Process::set_EnableRaisingEvents(bool)
0x2b2c  ldarg.0
0x2b2d  ldfld    class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ProcessLaunchers.DefaultProcessLauncher::_processConfig
0x2b32  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Path()
0x2b37  call     string Microsoft.BIServer.BIService.Paths::RelativeToBaseDirectory(string relativeDirectory)
0x2b3c  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x2b41  stloc.1
0x2b42  ldstr    aStartingProces// "Starting Process: "
0x2b47  ldloc.1
0x2b48  call     string [mscorlib]System.String::Concat(string, string)
0x2b4d  call     T0x2B000001
0x2b52  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x2b57  ldloc.0
0x2b58  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x2b5d  ldloc.1
0x2b5e  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_FileName(string)
0x2b63  ldloc.0
0x2b64  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x2b69  ldc.i4.0
0x2b6a  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_UseShellExecute(bool)
0x2b6f  ldloc.0
0x2b70  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x2b75  ldloc.1
0x2b76  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x2b7b  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_WorkingDirectory(string)
0x2b80  ldloc.0
0x2b81  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x2b86  ldarg.0
0x2b87  ldfld    class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ProcessLaunchers.DefaultProcessLauncher::_processConfig
0x2b8c  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Parameters()
0x2b91  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_Arguments(string)
0x2b96  ldarg.0
0x2b97  ldfld    class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ProcessLaunchers.DefaultProcessLauncher::_processConfig
0x2b9c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0x2ba1  brfalse.s loc_2C08
0x2ba3  ldarg.0
0x2ba4  ldfld    class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ProcessLaunchers.DefaultProcessLauncher::_processConfig
0x2ba9  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0x2bae  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Count()
0x2bb3  ldc.i4.0
0x2bb4  ble.s    loc_2C08
0x2bb6  ldarg.0
0x2bb7  ldfld    class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ProcessLaunchers.DefaultProcessLauncher::_processConfig
0x2bbc  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0x2bc1  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x2bc6  stloc.2
0x2bc7  br.s     loc_2BEF
0x2bc9  ldloca.s 2
0x2bcb  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x2bd0  stloc.3
0x2bd1  ldloc.0
0x2bd2  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x2bd7  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System]System.Diagnostics.ProcessStartInfo::get_EnvironmentVariables()
0x2bdc  ldloca.s 3
0x2bde  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x2be3  ldloca.s 3
0x2be5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x2bea  callvirt instance void [System]System.Collections.Specialized.StringDictionary::set_Item(string, string)
0x2bef  ldloca.s 2
0x2bf1  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x2bf6  brtrue.s loc_2BC9
0x2bf8  leave.s  loc_2C08
0x2bfa  ldloca.s 2
0x2bfc  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x2c02  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2c07  endfinally
0x2c08  ldloc.0
0x2c09  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x2c0e  ldc.i4.1
0x2c0f  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_WindowStyle(valuetype [System]System.Diagnostics.ProcessWindowStyle)
0x2c14  ldloc.0
0x2c15  callvirt instance bool [System]System.Diagnostics.Process::Start()
0x2c1a  brtrue.s loc_2C39
0x2c1c  ldstr    aProcessNotStar// "Process not started (may already be run"...
0x2c21  ldc.i4.1
0x2c22  newarr   [mscorlib]System.Object
0x2c27  dup
0x2c28  ldc.i4.0
0x2c29  ldarg.0
0x2c2a  callvirt instance string [mscorlib]System.Object::ToString()
0x2c2f  stelem.ref
0x2c30  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0x2c35  ldnull
0x2c36  stloc.0
0x2c37  br.s     loc_2C44
0x2c39  ldloc.0
0x2c3a  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x2c3f  call     void Microsoft.BIServer.BIService.ProcessBinder::Bind(int32 processId)
0x2c44  ldloc.0
0x2c45  stloc.s  4
0x2c47  leave.s  loc_2C5D
0x2c49  ldstr    aExceptionStart// "Exception starting process."
0x2c4e  call     T0x2B000001
0x2c53  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(class [mscorlib]System.Exception, string, object[])
0x2c58  ldnull
0x2c59  stloc.s  4
0x2c5b  leave.s  loc_2C5D
0x2c5d  ldloc.s  4
0x2c5f  ret
```
