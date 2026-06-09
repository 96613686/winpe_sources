# System.Deployment.Application.ComponentStore::PrepareStageAppComponent

- ea: `0xf280`
- end: `0xf332`
- name: `System.Deployment.Application.ComponentStore::PrepareStageAppComponent`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0xef90`

## callees

- `0x2260`
- `0x2f20`
- `0xd5e0`
- `0xf280`
- `0xf340`
- `0xf380`
- `0x25100`
- `0x251a0`

## string_xrefs

- `0xf2ab`: `commitParams`

## pseudocode

```c

```

## disassembly

```asm
0xf280  ldarg.2
0xf281  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.CommitApplicationParams::AppId
0xf286  stloc.0
0xf287  ldarg.2
0xf288  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0xf28d  stloc.1
0xf28e  ldarg.2
0xf28f  ldfld    string System.Deployment.Application.CommitApplicationParams::AppManifestPath
0xf294  stloc.2
0xf295  ldarg.2
0xf296  ldfld    string System.Deployment.Application.CommitApplicationParams::AppPayloadPath
0xf29b  stloc.3
0xf29c  ldarg.2
0xf29d  ldfld    string System.Deployment.Application.CommitApplicationParams::AppGroup
0xf2a2  stloc.s  4
0xf2a4  ldloc.s  4
0xf2a6  brtrue.s loc_F2C8
0xf2a8  ldloc.2
0xf2a9  brtrue.s loc_F2B6
0xf2ab  ldstr    aCommitparams// "commitParams"
0xf2b0  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf2b5  throw
0xf2b6  ldarg.1
0xf2b7  ldloc.0
0xf2b8  callvirt instance class System.Deployment.Internal.Isolation.IDefinitionAppId System.Deployment.Application.DefinitionAppId::get_ComPointer()
0xf2bd  ldloc.2
0xf2be  newobj   instance void System.Deployment.Internal.Isolation.StoreOperationStageComponent::.ctor(class System.Deployment.Internal.Isolation.IDefinitionAppId app, string Manifest)
0xf2c3  callvirt instance void System.Deployment.Internal.Isolation.StoreTransaction::Add(valuetype System.Deployment.Internal.Isolation.StoreOperationStageComponent o)
0xf2c8  ldloc.1
0xf2c9  ldloc.s  4
0xf2cb  ldc.i4.1
0xf2cc  callvirt instance class System.Deployment.Application.Manifest.File[] System.Deployment.Application.Manifest.AssemblyManifest::GetFilesInGroup(string group, bool optionalOnly)
0xf2d1  stloc.s  5
0xf2d3  ldloc.s  5
0xf2d5  stloc.s  7
0xf2d7  ldc.i4.0
0xf2d8  stloc.s  8
0xf2da  br.s     loc_F2F5
0xf2dc  ldloc.s  7
0xf2de  ldloc.s  8
0xf2e0  ldelem.ref
0xf2e1  stloc.s  9
0xf2e3  ldarg.0
0xf2e4  ldarg.1
0xf2e5  ldloc.s  9
0xf2e7  ldloc.0
0xf2e8  ldnull
0xf2e9  ldloc.3
0xf2ea  call     instance void System.Deployment.Application.ComponentStore::PrepareInstallFile(class StoreTransactionContext storeTxn, class System.Deployment.Application.Manifest.File file, class System.Deployment.Application.DefinitionAppId appId, class System.Deployment.Application.DefinitionIdentity asmId, string asmPayloadPath)
0xf2ef  ldloc.s  8
0xf2f1  ldc.i4.1
0xf2f2  add
0xf2f3  stloc.s  8
0xf2f5  ldloc.s  8
0xf2f7  ldloc.s  7
0xf2f9  ldlen
0xf2fa  conv.i4
0xf2fb  blt.s    loc_F2DC
0xf2fd  ldloc.1
0xf2fe  ldloc.s  4
0xf300  ldc.i4.1
0xf301  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly[] System.Deployment.Application.Manifest.AssemblyManifest::GetPrivateAssembliesInGroup(string group, bool optionalOnly)
0xf306  stloc.s  6
0xf308  ldloc.s  6
0xf30a  stloc.s  0xA
0xf30c  ldc.i4.0
0xf30d  stloc.s  0xB
0xf30f  br.s     loc_F329
0xf311  ldloc.s  0xA
0xf313  ldloc.s  0xB
0xf315  ldelem.ref
0xf316  stloc.s  0xC
0xf318  ldarg.0
0xf319  ldarg.1
0xf31a  ldloc.s  0xC
0xf31c  ldloc.0
0xf31d  ldloc.3
0xf31e  call     instance void System.Deployment.Application.ComponentStore::PrepareInstallPrivateAssembly(class StoreTransactionContext storeTxn, class System.Deployment.Application.Manifest.DependentAssembly privAsm, class System.Deployment.Application.DefinitionAppId appId, string appPayloadPath)
0xf323  ldloc.s  0xB
0xf325  ldc.i4.1
0xf326  add
0xf327  stloc.s  0xB
0xf329  ldloc.s  0xB
0xf32b  ldloc.s  0xA
0xf32d  ldlen
0xf32e  conv.i4
0xf32f  blt.s    loc_F311
0xf331  ret
```
