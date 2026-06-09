# System.Deployment.Application.Manifest.AssemblyManifest::ExtractIdentityFromCompLibAssembly

- ea: `0x25710`
- end: `0x25757`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::ExtractIdentityFromCompLibAssembly`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x25870`

## callees

- `0x17cd0`
- `0x193c0`
- `0x19440`
- `0x23900`
- `0x25710`

## string_xrefs

- `0x25710`: `AssemblyManifest.ExtractIdentityFromCompLibAssembly(`

## pseudocode

```c

```

## disassembly

```asm
0x25710  ldstr    aAssemblymanife// "AssemblyManifest.ExtractIdentityFromCom"...
0x25715  ldarg.0
0x25716  ldstr    aCalled// ") called."
0x2571b  call     string [mscorlib]System.String::Concat(string, string, string)
0x25720  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x25725  ldarg.0
0x25726  newobj   instance void System.Deployment.Application.AssemblyMetaDataImport::.ctor(string sourceFile)
0x2572b  stloc.0
0x2572c  ldloc.0
0x2572d  callvirt instance class [mscorlib]System.Reflection.AssemblyName System.Deployment.Application.AssemblyMetaDataImport::get_Name()
0x25732  stloc.1
0x25733  ldarg.0
0x25734  call     class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Win32InterOp.SystemUtils::GetDefinitionIdentityFromManagedAssembly(string filePath)
0x25739  stloc.2
0x2573a  leave.s  loc_25755
0x2573c  ldloc.0
0x2573d  brfalse.s loc_25745
0x2573f  ldloc.0
0x25740  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25745  endfinally
0x25746  pop
0x25747  ldnull
0x25748  stloc.2
0x25749  leave.s  loc_25755
0x2574b  pop
0x2574c  ldnull
0x2574d  stloc.2
0x2574e  leave.s  loc_25755
0x25750  pop
0x25751  ldnull
0x25752  stloc.2
0x25753  leave.s  loc_25755
0x25755  ldloc.2
0x25756  ret
```
