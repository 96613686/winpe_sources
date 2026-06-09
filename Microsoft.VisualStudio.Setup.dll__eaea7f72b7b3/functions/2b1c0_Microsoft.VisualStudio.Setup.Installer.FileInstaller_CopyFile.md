# Microsoft.VisualStudio.Setup.Installer.FileInstaller::CopyFile

- ea: `0x2b1c0`
- end: `0x2b3bd`
- name: `Microsoft.VisualStudio.Setup.Installer.FileInstaller::CopyFile`
- size: `509`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x34540`
- `0x35200`

## callees

- `0xfbb0`
- `0x10130`
- `0x11d60`
- `0x27f20`
- `0x2b1c0`
- `0x2b9e0`
- `0x3ea20`

## string_xrefs

- `0x2b296`: `' and scheduling the move after reboot.`
- `0x2b2f3`: `Copying file {0} to {1}`
- `0x2b383`: `Timestamp updated for file '`
- `0x2b3a1`: `Failed to update timestamp for file '`

## pseudocode

```c

```

## disassembly

```asm
0x2b1c0  ldarg.s  4
0x2b1c2  ldc.i4.0
0x2b1c3  stind.i4
0x2b1c4  ldarg.0
0x2b1c5  ldfld    class Microsoft.VisualStudio.Setup.Services.IPendingRebootOperations Microsoft.VisualStudio.Setup.Installer.FileInstaller::rebootPendingOperationsService
0x2b1ca  dup
0x2b1cb  brtrue.s loc_2B1D1
0x2b1cd  pop
0x2b1ce  ldnull
0x2b1cf  br.s     loc_2B1D6
0x2b1d1  callvirt instance class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Services.IPendingRebootOperations::get_FilesToBeDeleted()
0x2b1d6  brfalse.s loc_2B1EF
0x2b1d8  ldarg.0
0x2b1d9  ldfld    class Microsoft.VisualStudio.Setup.Services.IPendingRebootOperations Microsoft.VisualStudio.Setup.Installer.FileInstaller::rebootPendingOperationsService
0x2b1de  callvirt instance class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Services.IPendingRebootOperations::get_FilesToBeDeleted()
0x2b1e3  ldarg.3
0x2b1e4  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x2b1e9  brfalse.s loc_2B1EF
0x2b1eb  ldarg.s  4
0x2b1ed  ldc.i4.1
0x2b1ee  stind.i4
0x2b1ef  ldarg.3
0x2b1f0  stloc.0
0x2b1f1  ldarg.s  4
0x2b1f3  ldind.i4
0x2b1f4  ldc.i4.1
0x2b1f5  bne.un.s loc_2B203
0x2b1f7  ldloc.0
0x2b1f8  ldsfld   string Microsoft.VisualStudio.Setup.Installer.FileInstaller::NewFilePrefix
0x2b1fd  call     string [mscorlib]System.String::Concat(string, string)
0x2b202  stloc.0
0x2b203  ldloc.0
0x2b204  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x2b209  stloc.1
0x2b20a  ldarg.0
0x2b20b  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x2b210  ldloc.1
0x2b211  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateDirectory(string)
0x2b216  ldnull
0x2b217  stloc.2
0x2b218  ldarg.0
0x2b219  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x2b21e  ldloc.0
0x2b21f  ldc.i4.2
0x2b220  ldc.i4   0x1F4
0x2b225  call     class [mscorlib]System.IO.Stream Microsoft.VisualStudio.Setup.Extensions::CreateFileWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem, string fileSystem, int32 path, [opt] int32 retryCount)
0x2b22a  stloc.2
0x2b22b  leave    loc_2B2C4
0x2b230  isinst   [mscorlib]System.Exception
0x2b235  dup
0x2b236  brtrue.s loc_2B23C
0x2b238  pop
0x2b239  ldc.i4.0
0x2b23a  br.s     loc_2B257
0x2b23c  stloc.s  4
0x2b23e  ldloc.s  4
0x2b240  isinst   [mscorlib]System.UnauthorizedAccessException
0x2b245  brtrue.s loc_2B253
0x2b247  ldloc.s  4
0x2b249  isinst   [mscorlib]System.IO.IOException
0x2b24e  ldnull
0x2b24f  cgt.un
0x2b251  br.s     loc_2B254
0x2b253  ldc.i4.1
0x2b254  ldc.i4.0
0x2b255  cgt.un
0x2b257  endfilter
0x2b259  pop
0x2b25a  ldarg.3
0x2b25b  ldloc.0
0x2b25c  ldc.i4.5
0x2b25d  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x2b262  brfalse.s loc_2B2C2
0x2b264  ldloc.0
0x2b265  ldsfld   string Microsoft.VisualStudio.Setup.Installer.FileInstaller::NewFilePrefix
0x2b26a  call     string [mscorlib]System.String::Concat(string, string)
0x2b26f  stloc.0
0x2b270  ldarg.s  6
0x2b272  brfalse.s loc_2B2AB
0x2b274  ldarg.s  6
0x2b276  ldc.i4.5
0x2b277  newarr   [mscorlib]System.String
0x2b27c  dup
0x2b27d  ldc.i4.0
0x2b27e  ldstr    aCreationOfFile// "Creation of file '"
0x2b283  stelem.ref
0x2b284  dup
0x2b285  ldc.i4.1
0x2b286  ldarg.3
0x2b287  stelem.ref
0x2b288  dup
0x2b289  ldc.i4.2
0x2b28a  ldstr    aFailedRetrying// "' failed. Retrying with '"
0x2b28f  stelem.ref
0x2b290  dup
0x2b291  ldc.i4.3
0x2b292  ldloc.0
0x2b293  stelem.ref
0x2b294  dup
0x2b295  ldc.i4.4
0x2b296  ldstr    aAndSchedulingT// "' and scheduling the move after reboot."
0x2b29b  stelem.ref
0x2b29c  call     string [mscorlib]System.String::Concat(string[])
0x2b2a1  call     T0x2B000003
0x2b2a6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2b2ab  ldarg.0
0x2b2ac  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x2b2b1  ldloc.0
0x2b2b2  ldc.i4.2
0x2b2b3  ldc.i4   0x1F4
0x2b2b8  call     class [mscorlib]System.IO.Stream Microsoft.VisualStudio.Setup.Extensions::CreateFileWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem, string fileSystem, int32 path, [opt] int32 retryCount)
0x2b2bd  stloc.2
0x2b2be  ldarg.s  4
0x2b2c0  ldc.i4.1
0x2b2c1  stind.i4
0x2b2c2  leave.s  loc_2B2C4
0x2b2c4  ldarg.s  5
0x2b2c6  ldloc.0
0x2b2c7  stind.ref
0x2b2c8  ldloc.2
0x2b2c9  brtrue.s loc_2B2EE
0x2b2cb  ldarg.s  6
0x2b2cd  brfalse.s loc_2B2EC
0x2b2cf  ldarg.s  6
0x2b2d1  ldnull
0x2b2d2  ldstr    aCreationOfFile// "Creation of file '"
0x2b2d7  ldloc.0
0x2b2d8  ldstr    aFailed_0// "' failed."
0x2b2dd  call     string [mscorlib]System.String::Concat(string, string, string)
0x2b2e2  call     T0x2B000003
0x2b2e7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x2b2ec  ldc.i4.0
0x2b2ed  ret
0x2b2ee  ldloc.2
0x2b2ef  stloc.s  5
0x2b2f1  ldarg.s  6
0x2b2f3  ldstr    aCopyingFile0To// "Copying file {0} to {1}"
0x2b2f8  ldc.i4.2
0x2b2f9  newarr   [mscorlib]System.Object
0x2b2fe  dup
0x2b2ff  ldc.i4.0
0x2b300  ldarg.1
0x2b301  stelem.ref
0x2b302  dup
0x2b303  ldc.i4.1
0x2b304  ldloc.0
0x2b305  stelem.ref
0x2b306  newobj   instance void Microsoft.VisualStudio.Setup.LogActionWrapper::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger log, string actionName, object[] args)
0x2b30b  stloc.s  6
0x2b30d  ldarg.2
0x2b30e  ldloc.2
0x2b30f  call     void Microsoft.VisualStudio.Setup.Utility.IOUtil::CopyStream(class [mscorlib]System.IO.Stream input, class [mscorlib]System.IO.Stream output)
0x2b314  leave.s  loc_2B32E
0x2b316  ldloc.s  6
0x2b318  brfalse.s loc_2B321
0x2b31a  ldloc.s  6
0x2b31c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b321  endfinally
0x2b322  ldloc.s  5
0x2b324  brfalse.s loc_2B32D
0x2b326  ldloc.s  5
0x2b328  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b32d  endfinally
0x2b32e  ldc.i4.1
0x2b32f  stloc.3
0x2b330  ldarg.s  4
0x2b332  ldind.i4
0x2b333  brfalse.s loc_2B351
0x2b335  ldarg.0
0x2b336  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.Installer.FileInstaller::lockedFiles
0x2b33b  ldloc.0
0x2b33c  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x2b341  ldarg.0
0x2b342  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x2b347  ldloc.0
0x2b348  ldarg.3
0x2b349  ldc.i4.1
0x2b34a  ldc.i4.1
0x2b34b  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::MoveFile(string, string, bool, bool)
0x2b350  stloc.3
0x2b351  ldloc.3
0x2b352  brfalse.s loc_2B3BB
0x2b354  ldarg.0
0x2b355  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x2b35a  ldloc.0
0x2b35b  ldloca.s 7
0x2b35d  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::get_Now()
0x2b362  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>::.ctor(var<u1>)
0x2b367  ldloca.s 8
0x2b369  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>
0x2b36f  ldloc.s  8
0x2b371  ldloc.s  7
0x2b373  ldc.i4.2
0x2b374  ldc.i4   0x1F4
0x2b379  ldc.i4.0
0x2b37a  call     bool Microsoft.VisualStudio.Setup.Extensions::SetFileTimeWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset> creationTime, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset> lastWriteTime, [opt] int32 retryCount, [opt] int32 retryDelay, [opt] bool throwOnFailure)
0x2b37f  brfalse.s loc_2B39F
0x2b381  ldarg.s  6
0x2b383  ldstr    aTimestampUpdat// "Timestamp updated for file '"
0x2b388  ldloc.0
0x2b389  ldstr    asc_7F7FA// "'."
0x2b38e  call     string [mscorlib]System.String::Concat(string, string, string)
0x2b393  call     T0x2B000003
0x2b398  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2b39d  br.s     loc_2B3BB
0x2b39f  ldarg.s  6
0x2b3a1  ldstr    aFailedToUpdate_0// "Failed to update timestamp for file '"
0x2b3a6  ldloc.0
0x2b3a7  ldstr    asc_7F7FA// "'."
0x2b3ac  call     string [mscorlib]System.String::Concat(string, string, string)
0x2b3b1  call     T0x2B000003
0x2b3b6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2b3bb  ldloc.3
0x2b3bc  ret
```
