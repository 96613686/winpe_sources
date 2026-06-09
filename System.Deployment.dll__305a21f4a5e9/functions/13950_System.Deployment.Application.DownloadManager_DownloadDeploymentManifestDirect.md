# System.Deployment.Application.DownloadManager::DownloadDeploymentManifestDirect

- ea: `0x13950`
- end: `0x139d4`
- name: `System.Deployment.Application.DownloadManager::DownloadDeploymentManifestDirect`
- size: `132`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x13180`
- `0x13230`

## callees

- `0xda80`
- `0x13950`
- `0x13b90`
- `0x147a0`
- `0x17cd0`
- `0x1fca0`
- `0x20b30`
- `0x23020`
- `0x24970`
- `0x24b90`

## string_xrefs

- `0x13950`: `DownloadDeploymentManifestDirect(`
- `0x139a8`: `Ex_DeploymentManifestNoVersion`
- `0x139c2`: `Ex_InvalidDeploymentManifest`

## pseudocode

```c

```

## disassembly

```asm
0x13950  ldstr    aDownloaddeploy_1// "DownloadDeploymentManifestDirect("
0x13955  ldarg.1
0x13956  ldind.ref
0x13957  dup
0x13958  brtrue.s loc_1395E
0x1395a  pop
0x1395b  ldnull
0x1395c  br.s     loc_13963
0x1395e  callvirt instance string [mscorlib]System.Object::ToString()
0x13963  ldstr    aCalled// ") called."
0x13968  call     string [mscorlib]System.String::Concat(string, string, string)
0x1396d  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x13972  ldarg.2
0x13973  ldarg.0
0x13974  ldstr    aApplication// ".application"
0x13979  callvirt instance class System.Deployment.Application.TempFile System.Deployment.Application.SubscriptionStore::AcquireTempFile(string suffix)
0x1397e  stind.ref
0x1397f  ldarg.1
0x13980  ldarg.2
0x13981  ldind.ref
0x13982  callvirt instance string System.Deployment.Application.TempFile::get_Path()
0x13987  ldarg.3
0x13988  ldarg.s  4
0x1398a  ldc.i4.1
0x1398b  ldarg.s  5
0x1398d  call     class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.DownloadManager::DownloadManifest(class [System]System.Uri& sourceUri, string targetPath, class System.Deployment.Application.IDownloadNotification notification, class System.Deployment.Application.DownloadOptions options, valuetype ManifestType manifestType, [out] class System.Deployment.Application.ServerInformation& serverInformation)
0x13992  stloc.0
0x13993  ldloc.0
0x13994  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x13999  callvirt instance class [mscorlib]System.Version System.Deployment.Application.DefinitionIdentity::get_Version()
0x1399e  ldnull
0x1399f  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x139a4  brfalse.s loc_139B8
0x139a6  ldc.i4.s 0x10
0x139a8  ldstr    aExDeploymentma// "Ex_DeploymentManifestNoVersion"
0x139ad  call     string System.Deployment.Application.Resources::GetString(string s)
0x139b2  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x139b7  throw
0x139b8  ldloc.0
0x139b9  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x139be  brtrue.s loc_139D2
0x139c0  ldc.i4.s 0x10
0x139c2  ldstr    aExInvaliddeplo// "Ex_InvalidDeploymentManifest"
0x139c7  call     string System.Deployment.Application.Resources::GetString(string s)
0x139cc  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x139d1  throw
0x139d2  ldloc.0
0x139d3  ret
```
