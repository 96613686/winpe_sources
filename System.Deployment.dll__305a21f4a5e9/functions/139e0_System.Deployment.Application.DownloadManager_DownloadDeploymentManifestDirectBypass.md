# System.Deployment.Application.DownloadManager::DownloadDeploymentManifestDirectBypass

- ea: `0x139e0`
- end: `0x13b8a`
- name: `System.Deployment.Application.DownloadManager::DownloadDeploymentManifestDirectBypass`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path, registry_config`

## callers

- `0x13480`

## callees

- `0xd530`
- `0xd960`
- `0xda80`
- `0x139e0`
- `0x13bb0`
- `0x147a0`
- `0x17cd0`
- `0x17d40`
- `0x19e90`
- `0x1a060`
- `0x1ed40`
- `0x1eee0`
- `0x1f800`
- `0x1f890`
- `0x1f8b0`
- `0x1fca0`
- `0x20b30`
- `0x23020`
- `0x24380`
- `0x24970`
- `0x24b90`
- `0x25050`

## string_xrefs

- `0x13b5c`: `Ex_DeploymentManifestNoVersion`
- `0x13b77`: `Ex_InvalidDeploymentManifest`
- `0x139e0`: `DownloadDeploymentManifestDirectBypass called.`
- `0x13b2b`: `Reparse the deployment manifest for validations.`

## pseudocode

```c

```

## disassembly

```asm
0x139e0  ldstr    aDownloaddeploy_2// "DownloadDeploymentManifestDirectBypass "...
0x139e5  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x139ea  ldarg.3
0x139eb  ldnull
0x139ec  stind.ref
0x139ed  ldarg.2
0x139ee  ldarg.0
0x139ef  ldstr    aApplication// ".application"
0x139f4  callvirt instance class System.Deployment.Application.TempFile System.Deployment.Application.SubscriptionStore::AcquireTempFile(string suffix)
0x139f9  stind.ref
0x139fa  ldarg.1
0x139fb  ldarg.2
0x139fc  ldind.ref
0x139fd  callvirt instance string System.Deployment.Application.TempFile::get_Path()
0x13a02  ldarg.s  4
0x13a04  ldarg.s  5
0x13a06  ldarg.s  6
0x13a08  call     void System.Deployment.Application.DownloadManager::DownloadManifestAsRawFile(class [System]System.Uri& sourceUri, string targetPath, class System.Deployment.Application.IDownloadNotification notification, class System.Deployment.Application.DownloadOptions options, [out] class System.Deployment.Application.ServerInformation& serverInformation)
0x13a0d  ldc.i4.0
0x13a0e  stloc.0
0x13a0f  ldnull
0x13a10  stloc.1
0x13a11  ldnull
0x13a12  stloc.2
0x13a13  ldnull
0x13a14  stloc.3
0x13a15  ldnull
0x13a16  stloc.s  4
0x13a18  ldarg.2
0x13a19  ldind.ref
0x13a1a  callvirt instance string System.Deployment.Application.TempFile::get_Path()
0x13a1f  call     class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.ManifestReader::FromDocumentNoValidation(string localPath)
0x13a24  stloc.1
0x13a25  ldloc.1
0x13a26  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x13a2b  stloc.2
0x13a2c  ldloc.1
0x13a2d  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.AssemblyManifest::get_MainDependentAssembly()
0x13a32  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x13a37  newobj   instance void System.Deployment.Application.DefinitionIdentity::.ctor(class System.Deployment.Application.ReferenceIdentity refId)
0x13a3c  stloc.3
0x13a3d  ldarg.1
0x13a3e  ldind.ref
0x13a3f  callvirt instance string [System]System.Uri::get_Query()
0x13a44  brfalse.s loc_13A55
0x13a46  ldarg.1
0x13a47  ldind.ref
0x13a48  callvirt instance string [System]System.Uri::get_Query()
0x13a4d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13a52  ldc.i4.0
0x13a53  bgt.s    loc_13A59
0x13a55  ldarg.1
0x13a56  ldind.ref
0x13a57  br.s     loc_13A66
0x13a59  ldarg.1
0x13a5a  ldind.ref
0x13a5b  ldc.i4.2
0x13a5c  callvirt instance string [System]System.Uri::GetLeftPart(valuetype [System]System.UriPartial)
0x13a61  newobj   instance void [System]System.Uri::.ctor(string)
0x13a66  stloc.s  6
0x13a68  ldloc.s  6
0x13a6a  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x13a6f  ldc.i4.2
0x13a70  newarr   System.Deployment.Application.DefinitionIdentity
0x13a75  dup
0x13a76  ldc.i4.0
0x13a77  ldloc.2
0x13a78  stelem.ref
0x13a79  dup
0x13a7a  ldc.i4.1
0x13a7b  ldloc.3
0x13a7c  stelem.ref
0x13a7d  newobj   instance void System.Deployment.Application.DefinitionAppId::.ctor(string codebase, class System.Deployment.Application.DefinitionIdentity[] idPath)
0x13a82  stloc.s  4
0x13a84  ldstr    aExpectedappid// "expectedAppId="
0x13a89  ldloc.s  4
0x13a8b  callvirt instance string [mscorlib]System.Object::ToString()
0x13a90  call     string [mscorlib]System.String::Concat(string, string)
0x13a95  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x13a9a  leave.s  loc_13AB0
0x13a9c  pop
0x13a9d  ldc.i4.1
0x13a9e  stloc.0
0x13a9f  leave.s  loc_13AB0
0x13aa1  pop
0x13aa2  ldc.i4.1
0x13aa3  stloc.0
0x13aa4  leave.s  loc_13AB0
0x13aa6  pop
0x13aa7  ldc.i4.1
0x13aa8  stloc.0
0x13aa9  leave.s  loc_13AB0
0x13aab  pop
0x13aac  ldc.i4.1
0x13aad  stloc.0
0x13aae  leave.s  loc_13AB0
0x13ab0  ldloc.0
0x13ab1  brtrue.s loc_13B21
0x13ab3  ldarg.0
0x13ab4  ldloc.1
0x13ab5  callvirt instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.Manifest.AssemblyManifest deployment)
0x13aba  stloc.s  7
0x13abc  ldc.i4.0
0x13abd  stloc.s  9
0x13abf  ldarg.0
0x13ac0  ldloca.s 8
0x13ac2  callvirt instance class [mscorlib]System.IO.FileStream System.Deployment.Application.SubscriptionStore::AcquireReferenceTransaction([out] int64& transactionId)
0x13ac7  stloc.s  0xA
0x13ac9  ldarg.0
0x13aca  ldloc.s  7
0x13acc  ldloc.s  4
0x13ace  ldloc.s  8
0x13ad0  callvirt instance bool System.Deployment.Application.SubscriptionStore::CheckAndReferenceApplication(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.DefinitionAppId appId, int64 transactionId)
0x13ad5  stloc.s  9
0x13ad7  leave.s  loc_13AE5
0x13ad9  ldloc.s  0xA
0x13adb  brfalse.s loc_13AE4
0x13add  ldloc.s  0xA
0x13adf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13ae4  endfinally
0x13ae5  ldloc.s  9
0x13ae7  brfalse.s loc_13AF9
0x13ae9  ldloc.s  4
0x13aeb  ldloc.s  7
0x13aed  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_CurrentBind()
0x13af2  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x13af7  brtrue.s loc_13B0B
0x13af9  ldc.i4.1
0x13afa  stloc.0
0x13afb  ldloc.s  9
0x13afd  brfalse.s loc_13B2B
0x13aff  ldstr    aApplicationIsF_1// "Application is found in store and but i"...
0x13b04  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x13b09  br.s     loc_13B2B
0x13b0b  ldstr    aApplicationIsF_2// "Application is found in store and it is"...
0x13b10  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x13b15  ldarg.3
0x13b16  ldloc.s  7
0x13b18  stind.ref
0x13b19  ldarg.3
0x13b1a  ldind.ref
0x13b1b  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0x13b20  ret
0x13b21  ldstr    aApplicationIsN// "Application is not found in store."
0x13b26  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x13b2b  ldstr    aReparseTheDepl// "Reparse the deployment manifest for val"...
0x13b30  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x13b35  ldarg.2
0x13b36  ldind.ref
0x13b37  callvirt instance string System.Deployment.Application.TempFile::get_Path()
0x13b3c  ldc.i4.1
0x13b3d  ldarg.1
0x13b3e  ldind.ref
0x13b3f  call     class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.ManifestReader::FromDocument(string localPath, valuetype ManifestType manifestType, class [System]System.Uri sourceUri)
0x13b44  stloc.s  5
0x13b46  ldloc.s  5
0x13b48  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x13b4d  callvirt instance class [mscorlib]System.Version System.Deployment.Application.DefinitionIdentity::get_Version()
0x13b52  ldnull
0x13b53  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x13b58  brfalse.s loc_13B6C
0x13b5a  ldc.i4.s 0x10
0x13b5c  ldstr    aExDeploymentma// "Ex_DeploymentManifestNoVersion"
0x13b61  call     string System.Deployment.Application.Resources::GetString(string s)
0x13b66  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x13b6b  throw
0x13b6c  ldloc.s  5
0x13b6e  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x13b73  brtrue.s loc_13B87
0x13b75  ldc.i4.s 0x10
0x13b77  ldstr    aExInvaliddeplo// "Ex_InvalidDeploymentManifest"
0x13b7c  call     string System.Deployment.Application.Resources::GetString(string s)
0x13b81  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x13b86  throw
0x13b87  ldloc.s  5
0x13b89  ret
```
