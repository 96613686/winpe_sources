# Microsoft.BIServer.Configuration.WMI.WmiProvider::InstallMof

- ea: `0x53a0`
- end: `0x5523`
- name: `Microsoft.BIServer.Configuration.WMI.WmiProvider::InstallMof`
- size: `387`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x4e90`
- `0x53a0`

## string_xrefs

- `0x53a0`: `Attempting to install MOF file`
- `0x53c4`: `no registry WmiWbemKey set`
- `0x53d2`: `Installation Directory`
- `0x53fc`: `mofcomp.exe`
- `0x54b1`: `Compile operation for mof file {0} failed. Exit code {1}`
- `0x54eb`: `bad MOF compiler`
- `0x54f6`: `bad MOF compile command`

## pseudocode

```c

```

## disassembly

```asm
0x53a0  ldstr    aAttemptingToIn// "Attempting to install MOF file"
0x53a5  call     T0x2B000015
0x53aa  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x53af  ldnull
0x53b0  stloc.0
0x53b1  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x53b6  ldstr    aSoftwareMicros_0// "SOFTWARE\\Microsoft\\WBEM"
0x53bb  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x53c0  stloc.1
0x53c1  ldloc.1
0x53c2  brtrue.s loc_53CF
0x53c4  ldstr    aNoRegistryWmiw// "no registry WmiWbemKey set"
0x53c9  newobj   instance void Microsoft.BIServer.Configuration.WMI.WmiException::.ctor(string message)
0x53ce  throw
0x53cf  ldloc.1
0x53d0  stloc.3
0x53d1  ldloc.1
0x53d2  ldstr    aInstallationDi// "Installation Directory"
0x53d7  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x53dc  castclass [mscorlib]System.String
0x53e1  stloc.0
0x53e2  ldloc.1
0x53e3  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::Close()
0x53e8  leave.s  loc_53F4
0x53ea  ldloc.3
0x53eb  brfalse.s loc_53F3
0x53ed  ldloc.3
0x53ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x53f3  endfinally
0x53f4  ldloc.0
0x53f5  call     string [mscorlib]System.Environment::ExpandEnvironmentVariables(string)
0x53fa  stloc.0
0x53fb  ldloc.0
0x53fc  ldstr    aMofcompExe// "mofcomp.exe"
0x5401  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5406  stloc.0
0x5407  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x540c  stloc.2
0x540d  ldloc.2
0x540e  ldstr    a0_1// "\"{0}\""
0x5413  ldarg.0
0x5414  ldfld    string Microsoft.BIServer.Configuration.WMI.WmiProvider::_mofFile
0x5419  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x541e  pop
0x541f  ldloc.2
0x5420  callvirt instance string [mscorlib]System.Object::ToString()
0x5425  pop
0x5426  ldloc.0
0x5427  ldloc.2
0x5428  callvirt instance string [mscorlib]System.Object::ToString()
0x542d  newobj   instance void [System]System.Diagnostics.ProcessStartInfo::.ctor(string, string)
0x5432  dup
0x5433  ldc.i4.0
0x5434  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_UseShellExecute(bool)
0x5439  dup
0x543a  ldc.i4.1
0x543b  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_RedirectStandardError(bool)
0x5440  dup
0x5441  ldc.i4.1
0x5442  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_RedirectStandardOutput(bool)
0x5447  ldstr    aRunning01// "Running: {0} {1}"
0x544c  ldloc.0
0x544d  ldloc.2
0x544e  callvirt instance string [mscorlib]System.Object::ToString()
0x5453  call     string [mscorlib]System.String::Format(string, object, object)
0x5458  call     T0x2B000015
0x545d  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x5462  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::Start(class [System]System.Diagnostics.ProcessStartInfo)
0x5467  stloc.s  4
0x5469  ldloc.s  4
0x546b  ldarg.0
0x546c  ldftn    instance void Microsoft.BIServer.Configuration.WMI.WmiProvider::OutputHandler(object sender, class [System]System.Diagnostics.DataReceivedEventArgs outLine)
0x5472  newobj   instance void [System]System.Diagnostics.DataReceivedEventHandler::.ctor(object, native int)
0x5477  callvirt instance void [System]System.Diagnostics.Process::add_OutputDataReceived(class [System]System.Diagnostics.DataReceivedEventHandler)
0x547c  ldloc.s  4
0x547e  ldarg.0
0x547f  ldftn    instance void Microsoft.BIServer.Configuration.WMI.WmiProvider::OutputHandler(object sender, class [System]System.Diagnostics.DataReceivedEventArgs outLine)
0x5485  newobj   instance void [System]System.Diagnostics.DataReceivedEventHandler::.ctor(object, native int)
0x548a  callvirt instance void [System]System.Diagnostics.Process::add_ErrorDataReceived(class [System]System.Diagnostics.DataReceivedEventHandler)
0x548f  ldloc.s  4
0x5491  callvirt instance void [System]System.Diagnostics.Process::BeginOutputReadLine()
0x5496  ldloc.s  4
0x5498  callvirt instance void [System]System.Diagnostics.Process::BeginErrorReadLine()
0x549d  ldloc.s  4
0x549f  callvirt instance void [System]System.Diagnostics.Process::WaitForExit()
0x54a4  ldloc.s  4
0x54a6  callvirt instance int32 [System]System.Diagnostics.Process::get_ExitCode()
0x54ab  stloc.s  5
0x54ad  ldloc.s  5
0x54af  brfalse.s loc_5514
0x54b1  ldstr    aCompileOperati// "Compile operation for mof file {0} fail"...
0x54b6  ldc.i4.2
0x54b7  newarr   [mscorlib]System.Object
0x54bc  dup
0x54bd  ldc.i4.0
0x54be  ldarg.0
0x54bf  ldfld    string Microsoft.BIServer.Configuration.WMI.WmiProvider::_mofFile
0x54c4  stelem.ref
0x54c5  dup
0x54c6  ldc.i4.1
0x54c7  ldloc.s  5
0x54c9  box      [mscorlib]System.Int32
0x54ce  stelem.ref
0x54cf  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x54d4  ldloc.s  5
0x54d6  ldc.i4.1
0x54d7  sub
0x54d8  switch   loc_54EB, loc_54F6, loc_5501
0x54e9  br.s     loc_550C
0x54eb  ldstr    aBadMofCompiler// "bad MOF compiler"
0x54f0  newobj   instance void Microsoft.BIServer.Configuration.WMI.WmiException::.ctor(string message)
0x54f5  throw
0x54f6  ldstr    aBadMofCompileC// "bad MOF compile command"
0x54fb  newobj   instance void Microsoft.BIServer.Configuration.WMI.WmiException::.ctor(string message)
0x5500  throw
0x5501  ldstr    aBadMofFile// "bad MOF file"
0x5506  newobj   instance void Microsoft.BIServer.Configuration.WMI.WmiException::.ctor(string message)
0x550b  throw
0x550c  ldloc.s  5
0x550e  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x5513  throw
0x5514  leave.s  loc_5522
0x5516  ldloc.s  4
0x5518  brfalse.s loc_5521
0x551a  ldloc.s  4
0x551c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5521  endfinally
0x5522  ret
```
