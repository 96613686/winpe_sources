# Microsoft.VisualStudio.Setup.Installer.FileInstaller::DeleteFile

- ea: `0x2b3c0`
- end: `0x2b55b`
- name: `Microsoft.VisualStudio.Setup.Installer.FileInstaller::DeleteFile`
- size: `411`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x31040`
- `0x32ec0`
- `0x34ec0`

## callees

- `0xfed0`
- `0x2b140`
- `0x2b3c0`
- `0x2b9e0`
- `0x3ea20`
- `0x6c640`

## string_xrefs

- `0x2b3fe`: `' file is already deleted.`
- `0x2b457`: `{0} file deleted.`
- `0x2b49a`: `{0} file is scheduled for deletion after the reboot.`
- `0x2b52f`: `' could not be deleted nor could it be scheduled for deletion until after the reboot.`

## pseudocode

```c

```

## disassembly

```asm
0x2b3c0  newobj   instance void <>c__DisplayClass15_0::.ctor()
0x2b3c5  stloc.0
0x2b3c6  ldloc.0
0x2b3c7  ldarg.3
0x2b3c8  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <>c__DisplayClass15_0::logger
0x2b3cd  ldloc.0
0x2b3ce  ldarg.1
0x2b3cf  stfld    string <>c__DisplayClass15_0::file
0x2b3d4  ldarg.0
0x2b3d5  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x2b3da  ldloc.0
0x2b3db  ldfld    string <>c__DisplayClass15_0::file
0x2b3e0  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x2b3e5  brtrue.s loc_2B418
0x2b3e7  ldloc.0
0x2b3e8  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <>c__DisplayClass15_0::logger
0x2b3ed  dup
0x2b3ee  brtrue.s loc_2B3F3
0x2b3f0  pop
0x2b3f1  br.s     loc_2B412
0x2b3f3  ldstr    asc_7FEB6// "'"
0x2b3f8  ldloc.0
0x2b3f9  ldfld    string <>c__DisplayClass15_0::file
0x2b3fe  ldstr    aFileIsAlreadyD// "' file is already deleted."
0x2b403  call     string [mscorlib]System.String::Concat(string, string, string)
0x2b408  call     T0x2B000003
0x2b40d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2b412  ldarg.s  4
0x2b414  ldc.i4.0
0x2b415  stind.i1
0x2b416  ldc.i4.1
0x2b417  ret
0x2b418  ldarg.0
0x2b419  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x2b41e  ldloc.0
0x2b41f  ldfld    string <>c__DisplayClass15_0::file
0x2b424  ldarg.s  4
0x2b426  ldc.i4.1
0x2b427  ldc.i4.2
0x2b428  ldc.i4   0x1F4
0x2b42d  ldloc.0
0x2b42e  ldftn    instance bool <>c__DisplayClass15_0::<DeleteFile>b__0(class [mscorlib]System.Exception ex, int32 attempt)
0x2b434  newobj   instance void class [mscorlib]System.Func`3<class [mscorlib]System.Exception, int32, bool>::.ctor(object, native int)
0x2b439  ldloc.0
0x2b43a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <>c__DisplayClass15_0::logger
0x2b43f  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteFileWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [out] bool& rebootRequired, [opt] bool rebootOK, [opt] int32 retryCount, [opt] int32 retryDelay, [opt] class [mscorlib]System.Func`3<class [mscorlib]System.Exception, int32, bool> errorAction, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x2b444  stloc.1
0x2b445  ldloc.1
0x2b446  brfalse.s loc_2B475
0x2b448  ldloc.0
0x2b449  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <>c__DisplayClass15_0::logger
0x2b44e  dup
0x2b44f  brtrue.s loc_2B457
0x2b451  pop
0x2b452  br       loc_2B543
0x2b457  ldstr    a0FileDeleted// "{0} file deleted."
0x2b45c  ldc.i4.1
0x2b45d  newarr   [mscorlib]System.Object
0x2b462  dup
0x2b463  ldc.i4.0
0x2b464  ldloc.0
0x2b465  ldfld    string <>c__DisplayClass15_0::file
0x2b46a  stelem.ref
0x2b46b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x2b470  br       loc_2B543
0x2b475  ldarg.0
0x2b476  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.Installer.FileInstaller::lockedFiles
0x2b47b  ldloc.0
0x2b47c  ldfld    string <>c__DisplayClass15_0::file
0x2b481  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x2b486  ldarg.s  4
0x2b488  ldind.u1
0x2b489  brfalse  loc_2B518
0x2b48e  ldloc.0
0x2b48f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <>c__DisplayClass15_0::logger
0x2b494  dup
0x2b495  brtrue.s loc_2B49A
0x2b497  pop
0x2b498  br.s     loc_2B4B3
0x2b49a  ldstr    a0FileIsSchedul// "{0} file is scheduled for deletion afte"...
0x2b49f  ldc.i4.1
0x2b4a0  newarr   [mscorlib]System.Object
0x2b4a5  dup
0x2b4a6  ldc.i4.0
0x2b4a7  ldloc.0
0x2b4a8  ldfld    string <>c__DisplayClass15_0::file
0x2b4ad  stelem.ref
0x2b4ae  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x2b4b3  ldarg.0
0x2b4b4  ldfld    class Microsoft.VisualStudio.Setup.Services.IPendingRebootOperations Microsoft.VisualStudio.Setup.Installer.FileInstaller::rebootPendingOperationsService
0x2b4b9  dup
0x2b4ba  brtrue.s loc_2B4C8
0x2b4bc  pop
0x2b4bd  ldloca.s 3
0x2b4bf  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x2b4c5  ldloc.3
0x2b4c6  br.s     loc_2B4EC
0x2b4c8  callvirt instance class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Services.IPendingRebootOperations::get_FilesToBeDeleted()
0x2b4cd  dup
0x2b4ce  brtrue.s loc_2B4DC
0x2b4d0  pop
0x2b4d1  ldloca.s 3
0x2b4d3  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x2b4d9  ldloc.3
0x2b4da  br.s     loc_2B4EC
0x2b4dc  ldloc.0
0x2b4dd  ldfld    string <>c__DisplayClass15_0::file
0x2b4e2  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x2b4e7  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x2b4ec  stloc.2
0x2b4ed  ldloca.s 2
0x2b4ef  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2b4f4  brfalse.s loc_2B543
0x2b4f6  ldloca.s 2
0x2b4f8  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x2b4fd  brtrue.s loc_2B543
0x2b4ff  ldarg.0
0x2b500  ldfld    class Microsoft.VisualStudio.Setup.Services.IPendingRebootOperations Microsoft.VisualStudio.Setup.Installer.FileInstaller::rebootPendingOperationsService
0x2b505  callvirt instance class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Services.IPendingRebootOperations::get_FilesToBeDeleted()
0x2b50a  ldloc.0
0x2b50b  ldfld    string <>c__DisplayClass15_0::file
0x2b510  callvirt instance bool class [System]System.Collections.Generic.ISet`1<string>::Add(var<u1>)
0x2b515  pop
0x2b516  br.s     loc_2B543
0x2b518  ldloc.0
0x2b519  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger <>c__DisplayClass15_0::logger
0x2b51e  dup
0x2b51f  brtrue.s loc_2B524
0x2b521  pop
0x2b522  br.s     loc_2B543
0x2b524  ldstr    aFile_0// "File '"
0x2b529  ldloc.0
0x2b52a  ldfld    string <>c__DisplayClass15_0::file
0x2b52f  ldstr    aCouldNotBeDele// "' could not be deleted nor could it be "...
0x2b534  call     string [mscorlib]System.String::Concat(string, string, string)
0x2b539  call     T0x2B000003
0x2b53e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x2b543  ldloc.1
0x2b544  ldarg.s  4
0x2b546  ldind.u1
0x2b547  or
0x2b548  brfalse.s loc_2B559
0x2b54a  ldarg.0
0x2b54b  ldloc.0
0x2b54c  ldfld    string <>c__DisplayClass15_0::file
0x2b551  ldarg.2
0x2b552  ldarg.s  5
0x2b554  call     instance void Microsoft.VisualStudio.Setup.Installer.FileInstaller::GetFolderAncestors(string pathToStartFrom, string rootDir, class [System]System.Collections.Generic.ISet`1<string> ancestors)
0x2b559  ldloc.1
0x2b55a  ret
```
