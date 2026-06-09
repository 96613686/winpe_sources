# Microsoft.VisualStudio.Setup.Activities.DeletePackagesFromCacheActivity::.ctor

- ea: `0x5c270`
- end: `0x5c2d8`
- name: `Microsoft.VisualStudio.Setup.Activities.DeletePackagesFromCacheActivity::.ctor`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x59650`

## string_xrefs

- `0x5c284`: `cacheManager`
- `0x5c290`: `deletedPackageResults`
- `0x5c2a7`: `packagesToDelete`

## pseudocode

```c

```

## disassembly

```asm
0x5c270  ldarg.0
0x5c271  ldarg.1
0x5c272  call     instance void Microsoft.VisualStudio.Setup.Activities.Activity::.ctor(class [mscorlib]System.IServiceProvider services)
0x5c277  ldarg.s  4
0x5c279  ldstr    aAsynccoordinat_0// "asyncCoordinator"
0x5c27e  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x5c283  ldarg.2
0x5c284  ldstr    aCachemanager// "cacheManager"
0x5c289  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x5c28e  ldarg.s  6
0x5c290  ldstr    aDeletedpackage// "deletedPackageResults"
0x5c295  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x5c29a  ldarg.3
0x5c29b  ldstr    aFilesystem// "fileSystem"
0x5c2a0  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x5c2a5  ldarg.s  5
0x5c2a7  ldstr    aPackagestodele// "packagesToDelete"
0x5c2ac  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x5c2b1  ldarg.0
0x5c2b2  ldarg.s  4
0x5c2b4  stfld    class Microsoft.VisualStudio.Setup.Activities.AsyncCoordinator Microsoft.VisualStudio.Setup.Activities.DeletePackagesFromCacheActivity::asyncCoordinator
0x5c2b9  ldarg.0
0x5c2ba  ldarg.2
0x5c2bb  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager Microsoft.VisualStudio.Setup.Activities.DeletePackagesFromCacheActivity::cacheManager
0x5c2c0  ldarg.0
0x5c2c1  ldarg.s  6
0x5c2c3  stfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Activities.DeletedPackageResult> Microsoft.VisualStudio.Setup.Activities.DeletePackagesFromCacheActivity::deletedPackageResults
0x5c2c8  ldarg.0
0x5c2c9  ldarg.3
0x5c2ca  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Activities.DeletePackagesFromCacheActivity::fileSystem
0x5c2cf  ldarg.0
0x5c2d0  ldarg.s  5
0x5c2d2  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage> Microsoft.VisualStudio.Setup.Activities.DeletePackagesFromCacheActivity::packagesToDelete
0x5c2d7  ret
```
