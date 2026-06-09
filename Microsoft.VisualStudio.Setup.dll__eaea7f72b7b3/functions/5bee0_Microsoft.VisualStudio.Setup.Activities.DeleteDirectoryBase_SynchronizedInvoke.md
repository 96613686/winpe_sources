# Microsoft.VisualStudio.Setup.Activities.DeleteDirectoryBase::SynchronizedInvoke

- ea: `0x5bee0`
- end: `0x5bffd`
- name: `Microsoft.VisualStudio.Setup.Activities.DeleteDirectoryBase::SynchronizedInvoke`
- size: `285`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0xffb0`
- `0x596d0`
- `0x596f0`
- `0x599a0`
- `0x5be60`
- `0x5be80`
- `0x5bea0`
- `0x5bee0`

## string_xrefs

- `0x5bf46`: ` directory deleted successfully.`
- `0x5bf71`: ` directory is scheduled for deletion after the reboot.`
- `0x5bfb1`: ` directory could not be deleted nor was it scheduled for deletion after the reboot.`
- `0x5bfd5`: `Failed to delete directory "`

## pseudocode

```c

```

## disassembly

```asm
0x5bee0  ldarg.0
0x5bee1  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x5bee6  ldc.i4.1
0x5bee7  call     T0x2B00000C
0x5beec  stloc.0
0x5beed  ldarg.0
0x5beee  call     instance string Microsoft.VisualStudio.Setup.Activities.DeleteDirectoryBase::get_Directory()
0x5bef3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5bef8  brtrue   loc_5BFFC
0x5befd  ldloc.0
0x5befe  ldarg.0
0x5beff  call     instance string Microsoft.VisualStudio.Setup.Activities.DeleteDirectoryBase::get_Directory()
0x5bf04  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x5bf09  brfalse  loc_5BFFC
0x5bf0e  ldloc.0
0x5bf0f  ldarg.0
0x5bf10  call     instance string Microsoft.VisualStudio.Setup.Activities.DeleteDirectoryBase::get_Directory()
0x5bf15  ldloca.s 1
0x5bf17  ldarg.0
0x5bf18  call     instance bool Microsoft.VisualStudio.Setup.Activities.DeleteDirectoryBase::get_RebootOK()
0x5bf1d  ldarg.0
0x5bf1e  call     instance bool Microsoft.VisualStudio.Setup.Activities.DeleteDirectoryBase::get_Recursive()
0x5bf23  ldc.i4.2
0x5bf24  ldc.i4   0x1F4
0x5bf29  ldnull
0x5bf2a  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteDirectoryWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [out] bool& rebootRequired, [opt] bool rebootOK, [opt] bool recursive, [opt] int32 retryCount, [opt] int32 retryDelay, [opt] class [mscorlib]System.Func`3<class [mscorlib]System.Exception, int32, bool> errorAction)
0x5bf2f  brfalse.s loc_5BF5C
0x5bf31  ldarg.0
0x5bf32  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5bf37  dup
0x5bf38  brtrue.s loc_5BF40
0x5bf3a  pop
0x5bf3b  br       loc_5BFC5
0x5bf40  ldarg.0
0x5bf41  call     instance string Microsoft.VisualStudio.Setup.Activities.DeleteDirectoryBase::get_Directory()
0x5bf46  ldstr    aDirectoryDelet// " directory deleted successfully."
0x5bf4b  call     string [mscorlib]System.String::Concat(string, string)
0x5bf50  call     T0x2B000003
0x5bf55  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5bf5a  br.s     loc_5BFC5
0x5bf5c  ldloc.1
0x5bf5d  brfalse.s loc_5BF9F
0x5bf5f  ldarg.0
0x5bf60  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5bf65  dup
0x5bf66  brtrue.s loc_5BF6B
0x5bf68  pop
0x5bf69  br.s     loc_5BF85
0x5bf6b  ldarg.0
0x5bf6c  call     instance string Microsoft.VisualStudio.Setup.Activities.DeleteDirectoryBase::get_Directory()
0x5bf71  ldstr    aDirectoryIsSch// " directory is scheduled for deletion af"...
0x5bf76  call     string [mscorlib]System.String::Concat(string, string)
0x5bf7b  call     T0x2B000003
0x5bf80  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5bf85  ldarg.0
0x5bf86  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x5bf8b  ldc.i4.0
0x5bf8c  call     T0x2B00012B
0x5bf91  stloc.2
0x5bf92  ldloc.2
0x5bf93  brfalse.s loc_5BFC5
0x5bf95  ldarg.0
0x5bf96  ldloc.2
0x5bf97  ldc.i4.1
0x5bf98  call     instance void Microsoft.VisualStudio.Setup.Activities.Activity::SetRestartManagerRebootState(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRestartManager restartManager, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RebootType rebootType)
0x5bf9d  br.s     loc_5BFC5
0x5bf9f  ldarg.0
0x5bfa0  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5bfa5  dup
0x5bfa6  brtrue.s loc_5BFAB
0x5bfa8  pop
0x5bfa9  br.s     loc_5BFC5
0x5bfab  ldarg.0
0x5bfac  call     instance string Microsoft.VisualStudio.Setup.Activities.DeleteDirectoryBase::get_Directory()
0x5bfb1  ldstr    aDirectoryCould// " directory could not be deleted nor was"...
0x5bfb6  call     string [mscorlib]System.String::Concat(string, string)
0x5bfbb  call     T0x2B000003
0x5bfc0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5bfc5  leave.s  loc_5BFFC
0x5bfc7  stloc.3
0x5bfc8  ldarg.0
0x5bfc9  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5bfce  dup
0x5bfcf  brtrue.s loc_5BFD4
0x5bfd1  pop
0x5bfd2  br.s     loc_5BFFA
0x5bfd4  ldloc.3
0x5bfd5  ldstr    aFailedToDelete_16// "Failed to delete directory \""
0x5bfda  ldarg.0
0x5bfdb  call     instance string Microsoft.VisualStudio.Setup.Activities.DeleteDirectoryBase::get_Directory()
0x5bfe0  ldstr    asc_A020C// "\": "
0x5bfe5  ldloc.3
0x5bfe6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5bfeb  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x5bff0  call     T0x2B000003
0x5bff5  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x5bffa  leave.s  loc_5BFFC
0x5bffc  ret
```
