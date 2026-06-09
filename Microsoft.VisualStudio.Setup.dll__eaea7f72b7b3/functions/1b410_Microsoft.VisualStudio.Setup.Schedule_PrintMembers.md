# Microsoft.VisualStudio.Setup.Schedule::PrintMembers

- ea: `0x1b410`
- end: `0x1b52a`
- name: `Microsoft.VisualStudio.Setup.Schedule::PrintMembers`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1b3d0`

## callees

- `0x1b280`
- `0x1b290`
- `0x1b2a0`
- `0x1b2b0`
- `0x1b2c0`
- `0x1b2d0`
- `0x1b2e0`
- `0x1b2f0`
- `0x1b300`
- `0x1b310`
- `0x1b330`

## string_xrefs

- `0x1b416`: `PackagesToInstallOrUninstall = `
- `0x1b42f`: `, PackagesToInstall = `
- `0x1b448`: `, PackagesToUninstall = `
- `0x1b4ac`: `, ReverifyPackageCacheCoordinator = `
- `0x1b4c5`: `, InstallCoordinator = `

## pseudocode

```c

```

## disassembly

```asm
0x1b410  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::EnsureSufficientExecutionStack()
0x1b415  ldarg.1
0x1b416  ldstr    aPackagestoinst// "PackagesToInstallOrUninstall = "
0x1b41b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b420  pop
0x1b421  ldarg.1
0x1b422  ldarg.0
0x1b423  call     instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class Microsoft.VisualStudio.Setup.Activities.IActivity> Microsoft.VisualStudio.Setup.Schedule::get_PackagesToInstallOrUninstall()
0x1b428  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x1b42d  pop
0x1b42e  ldarg.1
0x1b42f  ldstr    aPackagestoinst_0// ", PackagesToInstall = "
0x1b434  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b439  pop
0x1b43a  ldarg.1
0x1b43b  ldarg.0
0x1b43c  call     instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class Microsoft.VisualStudio.Setup.Activities.IActivity> Microsoft.VisualStudio.Setup.Schedule::get_PackagesToInstall()
0x1b441  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x1b446  pop
0x1b447  ldarg.1
0x1b448  ldstr    aPackagestounin// ", PackagesToUninstall = "
0x1b44d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b452  pop
0x1b453  ldarg.1
0x1b454  ldarg.0
0x1b455  call     instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class Microsoft.VisualStudio.Setup.Activities.IActivity> Microsoft.VisualStudio.Setup.Schedule::get_PackagesToUninstall()
0x1b45a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x1b45f  pop
0x1b460  ldarg.1
0x1b461  ldstr    aPackagestoveri// ", PackagesToVerify = "
0x1b466  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b46b  pop
0x1b46c  ldarg.1
0x1b46d  ldarg.0
0x1b46e  call     instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class Microsoft.VisualStudio.Setup.Activities.IActivity> Microsoft.VisualStudio.Setup.Schedule::get_PackagesToVerify()
0x1b473  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x1b478  pop
0x1b479  ldarg.1
0x1b47a  ldstr    aPackagestodown// ", PackagesToDownload = "
0x1b47f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b484  pop
0x1b485  ldarg.1
0x1b486  ldarg.0
0x1b487  call     instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class Microsoft.VisualStudio.Setup.Activities.DownloadPackage> Microsoft.VisualStudio.Setup.Schedule::get_PackagesToDownload()
0x1b48c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x1b491  pop
0x1b492  ldarg.1
0x1b493  ldstr    aDownloadscoord// ", DownloadsCoordinator = "
0x1b498  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b49d  pop
0x1b49e  ldarg.1
0x1b49f  ldarg.0
0x1b4a0  call     instance class Microsoft.VisualStudio.Setup.Activities.AsyncCoordinator Microsoft.VisualStudio.Setup.Schedule::get_DownloadsCoordinator()
0x1b4a5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x1b4aa  pop
0x1b4ab  ldarg.1
0x1b4ac  ldstr    aReverifypackag// ", ReverifyPackageCacheCoordinator = "
0x1b4b1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b4b6  pop
0x1b4b7  ldarg.1
0x1b4b8  ldarg.0
0x1b4b9  call     instance class Microsoft.VisualStudio.Setup.Activities.Coordinator Microsoft.VisualStudio.Setup.Schedule::get_ReverifyPackageCacheCoordinator()
0x1b4be  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x1b4c3  pop
0x1b4c4  ldarg.1
0x1b4c5  ldstr    aInstallcoordin// ", InstallCoordinator = "
0x1b4ca  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b4cf  pop
0x1b4d0  ldarg.1
0x1b4d1  ldarg.0
0x1b4d2  call     instance class Microsoft.VisualStudio.Setup.Activities.Coordinator Microsoft.VisualStudio.Setup.Schedule::get_InstallCoordinator()
0x1b4d7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x1b4dc  pop
0x1b4dd  ldarg.1
0x1b4de  ldstr    aCancelcleanupc// ", CancelCleanupCoordinator = "
0x1b4e3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b4e8  pop
0x1b4e9  ldarg.1
0x1b4ea  ldarg.0
0x1b4eb  call     instance class Microsoft.VisualStudio.Setup.Activities.Coordinator Microsoft.VisualStudio.Setup.Schedule::get_CancelCleanupCoordinator()
0x1b4f0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x1b4f5  pop
0x1b4f6  ldarg.1
0x1b4f7  ldstr    aInitializer_0// ", Initializer = "
0x1b4fc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b501  pop
0x1b502  ldarg.1
0x1b503  ldarg.0
0x1b504  call     instance class Microsoft.VisualStudio.Setup.Activities.Initialize Microsoft.VisualStudio.Setup.Schedule::get_Initializer()
0x1b509  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x1b50e  pop
0x1b50f  ldarg.1
0x1b510  ldstr    aFinalizer// ", Finalizer = "
0x1b515  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b51a  pop
0x1b51b  ldarg.1
0x1b51c  ldarg.0
0x1b51d  call     instance class Microsoft.VisualStudio.Setup.Activities.Finalize Microsoft.VisualStudio.Setup.Schedule::get_Finalizer()
0x1b522  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x1b527  pop
0x1b528  ldc.i4.1
0x1b529  ret
```
