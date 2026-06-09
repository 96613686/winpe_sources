# Microsoft.VisualStudio.Setup.Activities.InstallExtension::Invoke

- ea: `0x5ef10`
- end: `0x5f029`
- name: `Microsoft.VisualStudio.Setup.Activities.InstallExtension::Invoke`
- size: `281`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x10ed0`
- `0x596d0`
- `0x5ef00`
- `0x5ef10`

## string_xrefs

- `0x5ef8c`: `Failed to install extensions via the VSIX installer.`
- `0x5efcb`: `Successfully installed VSIX extensions.`
- `0x5efe8`: `Timed out while trying to install VSIX extensions.`

## pseudocode

```c

```

## disassembly

```asm
0x5ef10  ldarg.0
0x5ef11  call     instance string Microsoft.VisualStudio.Setup.Activities.InstallExtension::get_Extension()
0x5ef16  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x5ef1b  brfalse.s loc_5EF1E
0x5ef1d  ret
0x5ef1e  nop
0x5ef1f  ldarg.0
0x5ef20  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Activities.InstallExtension::fileSystem
0x5ef25  call     string Microsoft.VisualStudio.Setup.Extensions::GetVSIXInstallerPath(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem)
0x5ef2a  stloc.0
0x5ef2b  ldarg.0
0x5ef2c  ldfld    string Microsoft.VisualStudio.Setup.Activities.InstallExtension::arguments
0x5ef31  ldarg.0
0x5ef32  ldfld    string Microsoft.VisualStudio.Setup.Activities.InstallExtension::instanceId
0x5ef37  ldstr    asc_853DA// " "
0x5ef3c  ldarg.0
0x5ef3d  call     instance string Microsoft.VisualStudio.Setup.Activities.InstallExtension::get_Extension()
0x5ef42  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x5ef47  stloc.1
0x5ef48  ldarg.0
0x5ef49  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService Microsoft.VisualStudio.Setup.Activities.InstallExtension::processService
0x5ef4e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService::CreateProcess()
0x5ef53  stloc.2
0x5ef54  ldloc.2
0x5ef55  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x5ef5a  ldloc.0
0x5ef5b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_FileName(string)
0x5ef60  ldloc.2
0x5ef61  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x5ef66  ldc.i4.1
0x5ef67  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_CreateNoWindow(bool)
0x5ef6c  ldloc.2
0x5ef6d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x5ef72  ldloc.1
0x5ef73  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_Arguments(string)
0x5ef78  ldloc.2
0x5ef79  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess::Start()
0x5ef7e  brtrue.s loc_5EFA0
0x5ef80  ldarg.0
0x5ef81  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5ef86  dup
0x5ef87  brtrue.s loc_5EF8C
0x5ef89  pop
0x5ef8a  br.s     loc_5EF9B
0x5ef8c  ldstr    aFailedToInstal// "Failed to install extensions via the VS"...
0x5ef91  call     T0x2B000003
0x5ef96  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5ef9b  leave    loc_5F028
0x5efa0  ldc.r8   5.0
0x5efa9  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x5efae  stloc.3
0x5efaf  ldloc.2
0x5efb0  ldloca.s 3
0x5efb2  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x5efb7  conv.i4
0x5efb8  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess::WaitForExit(int32)
0x5efbd  brfalse.s loc_5EFDC
0x5efbf  ldarg.0
0x5efc0  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5efc5  dup
0x5efc6  brtrue.s loc_5EFCB
0x5efc8  pop
0x5efc9  br.s     loc_5EFF7
0x5efcb  ldstr    aSuccessfullyIn// "Successfully installed VSIX extensions."
0x5efd0  call     T0x2B000003
0x5efd5  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5efda  br.s     loc_5EFF7
0x5efdc  ldarg.0
0x5efdd  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5efe2  dup
0x5efe3  brtrue.s loc_5EFE8
0x5efe5  pop
0x5efe6  br.s     loc_5EFF7
0x5efe8  ldstr    aTimedOutWhileT// "Timed out while trying to install VSIX "...
0x5efed  call     T0x2B000003
0x5eff2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5eff7  leave.s  loc_5F003
0x5eff9  ldloc.2
0x5effa  brfalse.s loc_5F002
0x5effc  ldloc.2
0x5effd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5f002  endfinally
0x5f003  leave.s  loc_5F028
0x5f005  stloc.s  4
0x5f007  ldarg.0
0x5f008  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5f00d  dup
0x5f00e  brtrue.s loc_5F013
0x5f010  pop
0x5f011  br.s     loc_5F026
0x5f013  ldloc.s  4
0x5f015  ldloc.s  4
0x5f017  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5f01c  call     T0x2B000003
0x5f021  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x5f026  leave.s  loc_5F028
0x5f028  ret
```
