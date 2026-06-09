# Microsoft.VisualStudio.Setup.Activities.DeletePackageFromCacheActivity::Invoke

- ea: `0x5c0e0`
- end: `0x5c252`
- name: `Microsoft.VisualStudio.Setup.Activities.DeletePackageFromCacheActivity::Invoke`
- size: `370`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0xfed0`
- `0x596d0`
- `0x5c010`
- `0x5c0d0`
- `0x5c0e0`

## string_xrefs

- `0x5c1a9`: `Failed to delete file '`
- `0x5c1fe`: `Failed to delete package '`

## pseudocode

```c

```

## disassembly

```asm
0x5c0e0  ldarg.0
0x5c0e1  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5c0e6  ldstr    aDeletingPackag// "Deleting package '"
0x5c0eb  ldarg.0
0x5c0ec  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage Microsoft.VisualStudio.Setup.Activities.DeletePackageFromCacheActivity::packageToDelete
0x5c0f1  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x5c0f6  ldstr    asc_7FEB6// "'"
0x5c0fb  call     string [mscorlib]System.String::Concat(string, string, string)
0x5c100  call     T0x2B000003
0x5c105  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5c10a  ldarg.0
0x5c10b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager Microsoft.VisualStudio.Setup.Activities.DeletePackageFromCacheActivity::cacheManager
0x5c110  ldarg.0
0x5c111  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage Microsoft.VisualStudio.Setup.Activities.DeletePackageFromCacheActivity::packageToDelete
0x5c116  ldc.i4.1
0x5c117  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager::GetPackageCacheDirectory(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, bool)
0x5c11c  stloc.0
0x5c11d  ldarga.s 1
0x5c11f  call     instance bool [mscorlib]System.Threading.CancellationToken::get_IsCancellationRequested()
0x5c124  brfalse.s loc_5C12B
0x5c126  leave    loc_5C251
0x5c12b  ldarg.0
0x5c12c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage Microsoft.VisualStudio.Setup.Activities.DeletePackageFromCacheActivity::packageToDelete
0x5c131  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Payload> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetPayloads(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage)
0x5c136  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Payload>::GetEnumerator()
0x5c13b  stloc.1
0x5c13c  br       loc_5C1D1
0x5c141  ldloc.1
0x5c142  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Payload>::get_Current()
0x5c147  stloc.2
0x5c148  ldloc.0
0x5c149  ldloc.2
0x5c14a  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Payload::get_FileName()
0x5c14f  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5c154  stloc.3
0x5c155  ldarg.0
0x5c156  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage Microsoft.VisualStudio.Setup.Activities.DeletePackageFromCacheActivity::packageToDelete
0x5c15b  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageType [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::get_Type()
0x5c160  ldc.i4.1
0x5c161  bne.un.s loc_5C182
0x5c163  ldloc.0
0x5c164  ldsfld   string Microsoft.VisualStudio.Setup.Cache.DirectoryRepository::VsixPayloadName
0x5c169  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x5c16e  stloc.s  5
0x5c170  ldarg.0
0x5c171  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Activities.DeletePackageFromCacheActivity::fileSystem
0x5c176  ldloc.s  5
0x5c178  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x5c17d  brfalse.s loc_5C182
0x5c17f  ldloc.s  5
0x5c181  stloc.3
0x5c182  ldarg.0
0x5c183  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Activities.DeletePackageFromCacheActivity::fileSystem
0x5c188  ldloc.3
0x5c189  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x5c18e  brfalse.s loc_5C1D1
0x5c190  ldarg.0
0x5c191  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Activities.DeletePackageFromCacheActivity::fileSystem
0x5c196  ldloc.3
0x5c197  ldloca.s 4
0x5c199  ldc.i4.0
0x5c19a  ldc.i4.2
0x5c19b  ldc.i4   0x1F4
0x5c1a0  ldnull
0x5c1a1  ldnull
0x5c1a2  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteFileWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [out] bool& rebootRequired, [opt] bool rebootOK, [opt] int32 retryCount, [opt] int32 retryDelay, [opt] class [mscorlib]System.Func`3<class [mscorlib]System.Exception, int32, bool> errorAction, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x5c1a7  brtrue.s loc_5C1D1
0x5c1a9  ldstr    aFailedToDelete_17// "Failed to delete file '"
0x5c1ae  ldloc.3
0x5c1af  ldstr    asc_7F7FA// "'."
0x5c1b4  call     string [mscorlib]System.String::Concat(string, string, string)
0x5c1b9  pop
0x5c1ba  ldarg.0
0x5c1bb  ldarg.0
0x5c1bc  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage Microsoft.VisualStudio.Setup.Activities.DeletePackageFromCacheActivity::packageToDelete
0x5c1c1  ldc.i4.0
0x5c1c2  newobj   instance void Microsoft.VisualStudio.Setup.Activities.DeletedPackageResult::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage package, bool isDeleted)
0x5c1c7  call     instance void Microsoft.VisualStudio.Setup.Activities.DeletePackageFromCacheActivity::set_DeleteResult(class Microsoft.VisualStudio.Setup.Activities.DeletedPackageResult value)
0x5c1cc  leave    loc_5C251
0x5c1d1  ldloc.1
0x5c1d2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5c1d7  brtrue   loc_5C141
0x5c1dc  leave.s  loc_5C1E8
0x5c1de  ldloc.1
0x5c1df  brfalse.s loc_5C1E7
0x5c1e1  ldloc.1
0x5c1e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5c1e7  endfinally
0x5c1e8  ldarg.0
0x5c1e9  ldarg.0
0x5c1ea  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage Microsoft.VisualStudio.Setup.Activities.DeletePackageFromCacheActivity::packageToDelete
0x5c1ef  ldc.i4.1
0x5c1f0  newobj   instance void Microsoft.VisualStudio.Setup.Activities.DeletedPackageResult::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage package, bool isDeleted)
0x5c1f5  call     instance void Microsoft.VisualStudio.Setup.Activities.DeletePackageFromCacheActivity::set_DeleteResult(class Microsoft.VisualStudio.Setup.Activities.DeletedPackageResult value)
0x5c1fa  leave.s  loc_5C251
0x5c1fc  stloc.s  6
0x5c1fe  ldstr    aFailedToDelete_18// "Failed to delete package '"
0x5c203  ldarg.0
0x5c204  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage Microsoft.VisualStudio.Setup.Activities.DeletePackageFromCacheActivity::packageToDelete
0x5c209  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x5c20e  ldstr    asc_7F7FA// "'."
0x5c213  call     string [mscorlib]System.String::Concat(string, string, string)
0x5c218  stloc.s  7
0x5c21a  ldarg.0
0x5c21b  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5c220  ldloc.s  7
0x5c222  ldstr    asc_82BA2// ": "
0x5c227  ldloc.s  6
0x5c229  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5c22e  call     string [mscorlib]System.String::Concat(string, string, string)
0x5c233  call     T0x2B000003
0x5c238  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5c23d  ldarg.0
0x5c23e  ldarg.0
0x5c23f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage Microsoft.VisualStudio.Setup.Activities.DeletePackageFromCacheActivity::packageToDelete
0x5c244  ldc.i4.0
0x5c245  newobj   instance void Microsoft.VisualStudio.Setup.Activities.DeletedPackageResult::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage package, bool isDeleted)
0x5c24a  call     instance void Microsoft.VisualStudio.Setup.Activities.DeletePackageFromCacheActivity::set_DeleteResult(class Microsoft.VisualStudio.Setup.Activities.DeletedPackageResult value)
0x5c24f  leave.s  loc_5C251
0x5c251  ret
```
