# Microsoft.VisualStudio.Setup.Installer.FileInstaller::DeleteEmptyDirectories

- ea: `0x2b560`
- end: `0x2b63b`
- name: `Microsoft.VisualStudio.Setup.Installer.FileInstaller::DeleteEmptyDirectories`
- size: `219`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x31040`
- `0x328b0`
- `0x34ec0`

## callees

- `0xffb0`
- `0x11d60`
- `0x2b560`
- `0x2b9e0`

## string_xrefs

- `0x2b5de`: `Directory '`
- `0x2b5e4`: `' was already deleted.`
- `0x2b600`: `Directory '{0}' could not be deleted. Error: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x2b560  ldarg.1
0x2b561  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<string>::get_Count()
0x2b566  ldc.i4.0
0x2b567  ble      loc_2B63A
0x2b56c  ldarg.3
0x2b56d  ldstr    aDeletingEmptyD// "Deleting empty directories"
0x2b572  call     T0x2B000003
0x2b577  newobj   instance void Microsoft.VisualStudio.Setup.LogActionWrapper::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger log, string actionName, object[] args)
0x2b57c  stloc.0
0x2b57d  ldarg.1
0x2b57e  call     T0x2B00016A
0x2b583  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x2b588  stloc.1
0x2b589  br       loc_2B619
0x2b58e  ldloc.1
0x2b58f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x2b594  stloc.2
0x2b595  ldarg.0
0x2b596  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x2b59b  ldloc.2
0x2b59c  ldstr    asc_81126// "*"
0x2b5a1  ldc.i4.0
0x2b5a2  callvirt instance string[] [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::GetFileSystemEntries(string, string, bool)
0x2b5a7  ldlen
0x2b5a8  brtrue.s loc_2B5C4
0x2b5aa  ldarg.0
0x2b5ab  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x2b5b0  ldloc.2
0x2b5b1  ldloca.s 3
0x2b5b3  ldc.i4.0
0x2b5b4  ldc.i4.0
0x2b5b5  ldc.i4.2
0x2b5b6  ldc.i4   0x1F4
0x2b5bb  ldnull
0x2b5bc  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteDirectoryWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [out] bool& rebootRequired, [opt] bool rebootOK, [opt] bool recursive, [opt] int32 retryCount, [opt] int32 retryDelay, [opt] class [mscorlib]System.Func`3<class [mscorlib]System.Exception, int32, bool> errorAction)
0x2b5c1  pop
0x2b5c2  br.s     loc_2B5D7
0x2b5c4  ldarg.2
0x2b5c5  brfalse.s loc_2B5D7
0x2b5c7  ldarg.0
0x2b5c8  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_FileSystem()
0x2b5cd  ldloc.2
0x2b5ce  ldnull
0x2b5cf  ldc.i4.1
0x2b5d0  ldc.i4.0
0x2b5d1  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::MoveFile(string, string, bool, bool)
0x2b5d6  pop
0x2b5d7  leave.s  loc_2B619
0x2b5d9  pop
0x2b5da  ldarg.3
0x2b5db  brfalse.s loc_2B5F8
0x2b5dd  ldarg.3
0x2b5de  ldstr    aDirectory// "Directory '"
0x2b5e3  ldloc.2
0x2b5e4  ldstr    aWasAlreadyDele// "' was already deleted."
0x2b5e9  call     string [mscorlib]System.String::Concat(string, string, string)
0x2b5ee  call     T0x2B000003
0x2b5f3  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2b5f8  leave.s  loc_2B619
0x2b5fa  stloc.s  4
0x2b5fc  ldarg.3
0x2b5fd  brfalse.s loc_2B617
0x2b5ff  ldarg.3
0x2b600  ldstr    aDirectory0Coul// "Directory '{0}' could not be deleted. E"...
0x2b605  ldloc.2
0x2b606  ldloc.s  4
0x2b608  call     string [mscorlib]System.String::Format(string, object, object)
0x2b60d  call     T0x2B000003
0x2b612  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2b617  leave.s  loc_2B619
0x2b619  ldloc.1
0x2b61a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2b61f  brtrue   loc_2B58E
0x2b624  leave.s  loc_2B63A
0x2b626  ldloc.1
0x2b627  brfalse.s loc_2B62F
0x2b629  ldloc.1
0x2b62a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b62f  endfinally
0x2b630  ldloc.0
0x2b631  brfalse.s loc_2B639
0x2b633  ldloc.0
0x2b634  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b639  endfinally
0x2b63a  ret
```
