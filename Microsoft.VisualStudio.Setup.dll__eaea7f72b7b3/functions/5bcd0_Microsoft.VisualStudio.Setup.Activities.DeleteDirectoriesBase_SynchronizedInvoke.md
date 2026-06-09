# Microsoft.VisualStudio.Setup.Activities.DeleteDirectoriesBase::SynchronizedInvoke

- ea: `0x5bcd0`
- end: `0x5bdfc`
- name: `Microsoft.VisualStudio.Setup.Activities.DeleteDirectoriesBase::SynchronizedInvoke`
- size: `300`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0xffb0`
- `0x596d0`
- `0x596f0`
- `0x599a0`
- `0x5bc50`
- `0x5bc70`
- `0x5bc90`
- `0x5bcd0`

## string_xrefs

- `0x5bd37`: ` directory deleted successfully.`
- `0x5bd5d`: ` directory is scheduled for deletion after the reboot.`
- `0x5bd9b`: ` directory could not be deleted nor was it scheduled for deletion after the reboot.`
- `0x5bdc1`: `Failed to delete directory "`

## pseudocode

```c

```

## disassembly

```asm
0x5bcd0  ldarg.0
0x5bcd1  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x5bcd6  ldc.i4.1
0x5bcd7  call     T0x2B00000C
0x5bcdc  stloc.0
0x5bcdd  ldarg.0
0x5bcde  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.VisualStudio.Setup.Activities.DeleteDirectoriesBase::get_Directories()
0x5bce3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x5bce8  stloc.1
0x5bce9  br       loc_5BDE4
0x5bcee  ldloc.1
0x5bcef  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x5bcf4  stloc.2
0x5bcf5  ldloc.2
0x5bcf6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5bcfb  brtrue   loc_5BDE4
0x5bd00  ldloc.0
0x5bd01  ldloc.2
0x5bd02  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x5bd07  brfalse  loc_5BDE4
0x5bd0c  ldloc.0
0x5bd0d  ldloc.2
0x5bd0e  ldloca.s 3
0x5bd10  ldarg.0
0x5bd11  call     instance bool Microsoft.VisualStudio.Setup.Activities.DeleteDirectoriesBase::get_RebootOK()
0x5bd16  ldarg.0
0x5bd17  call     instance bool Microsoft.VisualStudio.Setup.Activities.DeleteDirectoriesBase::get_Recursive()
0x5bd1c  ldc.i4.2
0x5bd1d  ldc.i4   0x1F4
0x5bd22  ldnull
0x5bd23  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteDirectoryWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [out] bool& rebootRequired, [opt] bool rebootOK, [opt] bool recursive, [opt] int32 retryCount, [opt] int32 retryDelay, [opt] class [mscorlib]System.Func`3<class [mscorlib]System.Exception, int32, bool> errorAction)
0x5bd28  brfalse.s loc_5BD4D
0x5bd2a  ldarg.0
0x5bd2b  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5bd30  dup
0x5bd31  brtrue.s loc_5BD36
0x5bd33  pop
0x5bd34  br.s     loc_5BDAF
0x5bd36  ldloc.2
0x5bd37  ldstr    aDirectoryDelet// " directory deleted successfully."
0x5bd3c  call     string [mscorlib]System.String::Concat(string, string)
0x5bd41  call     T0x2B000003
0x5bd46  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5bd4b  br.s     loc_5BDAF
0x5bd4d  ldloc.3
0x5bd4e  brfalse.s loc_5BD8E
0x5bd50  ldarg.0
0x5bd51  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5bd56  dup
0x5bd57  brtrue.s loc_5BD5C
0x5bd59  pop
0x5bd5a  br.s     loc_5BD71
0x5bd5c  ldloc.2
0x5bd5d  ldstr    aDirectoryIsSch// " directory is scheduled for deletion af"...
0x5bd62  call     string [mscorlib]System.String::Concat(string, string)
0x5bd67  call     T0x2B000003
0x5bd6c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5bd71  ldarg.0
0x5bd72  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x5bd77  ldc.i4.0
0x5bd78  call     T0x2B00012B
0x5bd7d  stloc.s  4
0x5bd7f  ldloc.s  4
0x5bd81  brfalse.s loc_5BDAF
0x5bd83  ldarg.0
0x5bd84  ldloc.s  4
0x5bd86  ldc.i4.1
0x5bd87  call     instance void Microsoft.VisualStudio.Setup.Activities.Activity::SetRestartManagerRebootState(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRestartManager restartManager, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RebootType rebootType)
0x5bd8c  br.s     loc_5BDAF
0x5bd8e  ldarg.0
0x5bd8f  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5bd94  dup
0x5bd95  brtrue.s loc_5BD9A
0x5bd97  pop
0x5bd98  br.s     loc_5BDAF
0x5bd9a  ldloc.2
0x5bd9b  ldstr    aDirectoryCould// " directory could not be deleted nor was"...
0x5bda0  call     string [mscorlib]System.String::Concat(string, string)
0x5bda5  call     T0x2B000003
0x5bdaa  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5bdaf  leave.s  loc_5BDE4
0x5bdb1  stloc.s  5
0x5bdb3  ldarg.0
0x5bdb4  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5bdb9  dup
0x5bdba  brtrue.s loc_5BDBF
0x5bdbc  pop
0x5bdbd  br.s     loc_5BDE2
0x5bdbf  ldloc.s  5
0x5bdc1  ldstr    aFailedToDelete_16// "Failed to delete directory \""
0x5bdc6  ldloc.2
0x5bdc7  ldstr    asc_A020C// "\": "
0x5bdcc  ldloc.s  5
0x5bdce  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5bdd3  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x5bdd8  call     T0x2B000003
0x5bddd  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x5bde2  leave.s  loc_5BDE4
0x5bde4  ldloc.1
0x5bde5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5bdea  brtrue   loc_5BCEE
0x5bdef  leave.s  loc_5BDFB
0x5bdf1  ldloc.1
0x5bdf2  brfalse.s loc_5BDFA
0x5bdf4  ldloc.1
0x5bdf5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5bdfa  endfinally
0x5bdfb  ret
```
