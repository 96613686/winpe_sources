# System.Deployment.Application.ComponentStore::PrepareInstallPrivateAssembly

- ea: `0xf380`
- end: `0xf419`
- name: `System.Deployment.Application.ComponentStore::PrepareInstallPrivateAssembly`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0xf280`

## callees

- `0x2270`
- `0x2f20`
- `0xd5e0`
- `0xdc20`
- `0xf340`
- `0xf380`
- `0x18f40`
- `0x24380`
- `0x243c0`
- `0x248b0`
- `0x24950`
- `0x24970`
- `0x24dd0`

## pseudocode

```c

```

## disassembly

```asm
0xf380  ldarg.2
0xf381  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_CodebaseFS()
0xf386  stloc.0
0xf387  ldarg.s  4
0xf389  ldloc.0
0xf38a  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xf38f  stloc.1
0xf390  ldloc.1
0xf391  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0xf396  stloc.2
0xf397  ldloc.1
0xf398  newobj   instance void System.Deployment.Application.Manifest.AssemblyManifest::.ctor(string filePath)
0xf39d  stloc.3
0xf39e  ldloc.3
0xf39f  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0xf3a4  stloc.s  4
0xf3a6  ldloc.3
0xf3a7  callvirt instance string System.Deployment.Application.Manifest.AssemblyManifest::get_RawXmlFilePath()
0xf3ac  stloc.s  5
0xf3ae  ldloc.s  5
0xf3b0  brtrue.s loc_F3CF
0xf3b2  ldloc.1
0xf3b3  ldstr    aGenman// ".genman"
0xf3b8  call     string [mscorlib]System.String::Concat(string, string)
0xf3bd  stloc.s  5
0xf3bf  ldarg.2
0xf3c0  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0xf3c5  ldloc.3
0xf3c6  ldloc.s  5
0xf3c8  call     class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.ManifestGenerator::GenerateManifest(class System.Deployment.Application.ReferenceIdentity suggestedReferenceIdentity, class System.Deployment.Application.Manifest.AssemblyManifest manifest, string outputManifest)
0xf3cd  stloc.s  4
0xf3cf  ldarg.1
0xf3d0  ldarg.3
0xf3d1  callvirt instance class System.Deployment.Internal.Isolation.IDefinitionAppId System.Deployment.Application.DefinitionAppId::get_ComPointer()
0xf3d6  ldloc.s  4
0xf3d8  callvirt instance class System.Deployment.Internal.Isolation.IDefinitionIdentity System.Deployment.Application.DefinitionIdentity::get_ComPointer()
0xf3dd  ldloc.s  5
0xf3df  newobj   instance void System.Deployment.Internal.Isolation.StoreOperationStageComponent::.ctor(class System.Deployment.Internal.Isolation.IDefinitionAppId app, class System.Deployment.Internal.Isolation.IDefinitionIdentity comp, string Manifest)
0xf3e4  callvirt instance void System.Deployment.Internal.Isolation.StoreTransaction::Add(valuetype System.Deployment.Internal.Isolation.StoreOperationStageComponent o)
0xf3e9  ldloc.3
0xf3ea  callvirt instance class System.Deployment.Application.Manifest.File[] System.Deployment.Application.Manifest.AssemblyManifest::get_Files()
0xf3ef  stloc.s  6
0xf3f1  ldc.i4.0
0xf3f2  stloc.s  7
0xf3f4  br.s     loc_F410
0xf3f6  ldloc.s  6
0xf3f8  ldloc.s  7
0xf3fa  ldelem.ref
0xf3fb  stloc.s  8
0xf3fd  ldarg.0
0xf3fe  ldarg.1
0xf3ff  ldloc.s  8
0xf401  ldarg.3
0xf402  ldloc.s  4
0xf404  ldloc.2
0xf405  call     instance void System.Deployment.Application.ComponentStore::PrepareInstallFile(class StoreTransactionContext storeTxn, class System.Deployment.Application.Manifest.File file, class System.Deployment.Application.DefinitionAppId appId, class System.Deployment.Application.DefinitionIdentity asmId, string asmPayloadPath)
0xf40a  ldloc.s  7
0xf40c  ldc.i4.1
0xf40d  add
0xf40e  stloc.s  7
0xf410  ldloc.s  7
0xf412  ldloc.s  6
0xf414  ldlen
0xf415  conv.i4
0xf416  blt.s    loc_F3F6
0xf418  ret
```
