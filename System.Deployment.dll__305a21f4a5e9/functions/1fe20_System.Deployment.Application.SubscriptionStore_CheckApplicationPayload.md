# System.Deployment.Application.SubscriptionStore::CheckApplicationPayload

- ea: `0x1fe20`
- end: `0x1ffae`
- name: `System.Deployment.Application.SubscriptionStore::CheckApplicationPayload`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x1f1c0`

## callees

- `0xe960`
- `0x103c0`
- `0x146f0`
- `0x17d40`
- `0x1ba00`
- `0x1fe20`
- `0x23020`
- `0x23970`
- `0x23db0`
- `0x24970`
- `0x24f90`
- `0x27fb0`

## string_xrefs

- `0x1fe9b`: `.manifest`
- `0x1fe84`: `manifests`
- `0x1ff16`: `In-place update check. Existing manifest path = `
- `0x1ff22`: `, Existing manifest hash=`
- `0x1ff38`: `, New manifest path=`
- `0x1ff49`: `, New manifest hash=`
- `0x1ff9d`: `Ex_ApplicationInplaceUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x1fe20  ldarg.1
0x1fe21  ldfld    string System.Deployment.Application.CommitApplicationParams::AppGroup
0x1fe26  brtrue.s loc_1FE5C
0x1fe28  ldarg.1
0x1fe29  ldfld    valuetype System.Deployment.Application.AppType System.Deployment.Application.CommitApplicationParams::appType
0x1fe2e  ldc.i4.3
0x1fe2f  beq.s    loc_1FE5C
0x1fe31  ldarg.1
0x1fe32  ldfld    string System.Deployment.Application.CommitApplicationParams::AppPayloadPath
0x1fe37  ldarg.1
0x1fe38  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0x1fe3d  callvirt instance class System.Deployment.Application.Manifest.EntryPoint[] System.Deployment.Application.Manifest.AssemblyManifest::get_EntryPoints()
0x1fe42  ldc.i4.0
0x1fe43  ldelem.ref
0x1fe44  callvirt instance string System.Deployment.Application.Manifest.EntryPoint::get_CommandFile()
0x1fe49  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1fe4e  stloc.0
0x1fe4f  call     bool System.Deployment.Application.PlatformDetector::IsWin8orLater()
0x1fe54  brtrue.s loc_1FE5C
0x1fe56  ldloc.0
0x1fe57  call     void System.Deployment.Application.Win32InterOp.SystemUtils::CheckSupportedImageAndCLRVersions(string path)
0x1fe5c  ldnull
0x1fe5d  stloc.1
0x1fe5e  ldnull
0x1fe5f  stloc.2
0x1fe60  ldarg.0
0x1fe61  ldfld    class System.Deployment.Application.ComponentStore System.Deployment.Application.SubscriptionStore::_compStore
0x1fe66  ldarg.1
0x1fe67  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0x1fe6c  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x1fe71  callvirt instance class IPathLock System.Deployment.Application.ComponentStore::LockAssemblyPath(class System.Deployment.Application.DefinitionIdentity asmId)
0x1fe76  stloc.2
0x1fe77  ldloc.2
0x1fe78  callvirt instance string IPathLock::get_Path()
0x1fe7d  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x1fe82  stloc.1
0x1fe83  ldloc.1
0x1fe84  ldstr    aManifests// "manifests"
0x1fe89  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1fe8e  stloc.1
0x1fe8f  ldloc.1
0x1fe90  ldloc.2
0x1fe91  callvirt instance string IPathLock::get_Path()
0x1fe96  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x1fe9b  ldstr    aManifest// ".manifest"
0x1fea0  call     string [mscorlib]System.String::Concat(string, string)
0x1fea5  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1feaa  stloc.1
0x1feab  leave.s  loc_1FEBD
0x1fead  pop
0x1feae  leave.s  loc_1FEBD
0x1feb0  pop
0x1feb1  leave.s  loc_1FEBD
0x1feb3  ldloc.2
0x1feb4  brfalse.s loc_1FEBC
0x1feb6  ldloc.2
0x1feb7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1febc  endfinally
0x1febd  ldloc.1
0x1febe  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1fec3  brtrue   loc_1FFAD
0x1fec8  ldloc.1
0x1fec9  call     bool [mscorlib]System.IO.File::Exists(string)
0x1fece  brfalse  loc_1FFAD
0x1fed3  ldarg.1
0x1fed4  ldfld    string System.Deployment.Application.CommitApplicationParams::AppManifestPath
0x1fed9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1fede  brtrue   loc_1FFAD
0x1fee3  ldarg.1
0x1fee4  ldfld    string System.Deployment.Application.CommitApplicationParams::AppManifestPath
0x1fee9  call     bool [mscorlib]System.IO.File::Exists(string)
0x1feee  brfalse  loc_1FFAD
0x1fef3  ldloc.1
0x1fef4  ldc.i4.1
0x1fef5  ldc.i4.1
0x1fef6  call     unsigned int8[] System.Deployment.Application.ComponentVerifier::GenerateDigestValue(string filePath, valuetype System.Deployment.Internal.Isolation.Manifest.CMS_HASH_DIGESTMETHOD digestMethod, valuetype System.Deployment.Internal.Isolation.Manifest.CMS_HASH_TRANSFORM transform)
0x1fefb  stloc.3
0x1fefc  ldarg.1
0x1fefd  ldfld    string System.Deployment.Application.CommitApplicationParams::AppManifestPath
0x1ff02  ldc.i4.1
0x1ff03  ldc.i4.1
0x1ff04  call     unsigned int8[] System.Deployment.Application.ComponentVerifier::GenerateDigestValue(string filePath, valuetype System.Deployment.Internal.Isolation.Manifest.CMS_HASH_DIGESTMETHOD digestMethod, valuetype System.Deployment.Internal.Isolation.Manifest.CMS_HASH_TRANSFORM transform)
0x1ff09  stloc.s  4
0x1ff0b  ldc.i4.0
0x1ff0c  stloc.s  5
0x1ff0e  ldc.i4.8
0x1ff0f  newarr   [mscorlib]System.String
0x1ff14  dup
0x1ff15  ldc.i4.0
0x1ff16  ldstr    aInPlaceUpdateC// "In-place update check. Existing manifes"...
0x1ff1b  stelem.ref
0x1ff1c  dup
0x1ff1d  ldc.i4.1
0x1ff1e  ldloc.1
0x1ff1f  stelem.ref
0x1ff20  dup
0x1ff21  ldc.i4.2
0x1ff22  ldstr    aExistingManife// ", Existing manifest hash="
0x1ff27  stelem.ref
0x1ff28  dup
0x1ff29  ldc.i4.3
0x1ff2a  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x1ff2f  ldloc.3
0x1ff30  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x1ff35  stelem.ref
0x1ff36  dup
0x1ff37  ldc.i4.4
0x1ff38  ldstr    aNewManifestPat// ", New manifest path="
0x1ff3d  stelem.ref
0x1ff3e  dup
0x1ff3f  ldc.i4.5
0x1ff40  ldarg.1
0x1ff41  ldfld    string System.Deployment.Application.CommitApplicationParams::AppManifestPath
0x1ff46  stelem.ref
0x1ff47  dup
0x1ff48  ldc.i4.6
0x1ff49  ldstr    aNewManifestHas// ", New manifest hash="
0x1ff4e  stelem.ref
0x1ff4f  dup
0x1ff50  ldc.i4.7
0x1ff51  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x1ff56  ldloc.s  4
0x1ff58  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x1ff5d  stelem.ref
0x1ff5e  call     string [mscorlib]System.String::Concat(string[])
0x1ff63  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1ff68  ldloc.3
0x1ff69  ldlen
0x1ff6a  conv.i4
0x1ff6b  ldloc.s  4
0x1ff6d  ldlen
0x1ff6e  conv.i4
0x1ff6f  bne.un.s loc_1FF98
0x1ff71  ldc.i4.0
0x1ff72  stloc.s  6
0x1ff74  br.s     loc_1FF87
0x1ff76  ldloc.3
0x1ff77  ldloc.s  6
0x1ff79  ldelem.u1
0x1ff7a  ldloc.s  4
0x1ff7c  ldloc.s  6
0x1ff7e  ldelem.u1
0x1ff7f  bne.un.s loc_1FF8E
0x1ff81  ldloc.s  6
0x1ff83  ldc.i4.1
0x1ff84  add
0x1ff85  stloc.s  6
0x1ff87  ldloc.s  6
0x1ff89  ldloc.3
0x1ff8a  ldlen
0x1ff8b  conv.i4
0x1ff8c  blt.s    loc_1FF76
0x1ff8e  ldloc.s  6
0x1ff90  ldloc.3
0x1ff91  ldlen
0x1ff92  conv.i4
0x1ff93  blt.s    loc_1FF98
0x1ff95  ldc.i4.1
0x1ff96  stloc.s  5
0x1ff98  ldloc.s  5
0x1ff9a  brtrue.s loc_1FFAD
0x1ff9c  ldc.i4.7
0x1ff9d  ldstr    aExApplicationi// "Ex_ApplicationInplaceUpdate"
0x1ffa2  call     string System.Deployment.Application.Resources::GetString(string s)
0x1ffa7  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x1ffac  throw
0x1ffad  ret
```
