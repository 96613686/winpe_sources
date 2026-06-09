# System.Deployment.Application.Manifest.AssemblyManifest::LoadFromPEResources

- ea: `0x25670`
- end: `0x25702`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::LoadFromPEResources`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x25870`

## callees

- `0xdc90`
- `0x17d40`
- `0x236c0`
- `0x24970`
- `0x24a70`
- `0x25360`
- `0x25670`
- `0x27390`

## string_xrefs

- `0x256f6`: `File does not contain ID_1 manifest.`

## pseudocode

```c

```

## disassembly

```asm
0x25670  ldnull
0x25671  stloc.0
0x25672  ldarg.1
0x25673  call     unsigned int8[] System.Deployment.Application.Win32InterOp.SystemUtils::GetManifestFromPEResources(string filePath)
0x25678  stloc.0
0x25679  leave.s  loc_25685
0x2567b  stloc.1
0x2567c  ldloc.1
0x2567d  ldarg.1
0x2567e  call     void System.Deployment.Application.Manifest.AssemblyManifest::ManifestLoadExceptionHelper(class [mscorlib]System.Exception exception, string filePath)
0x25683  leave.s  loc_25685
0x25685  ldloc.0
0x25686  brfalse.s loc_256F6
0x25688  ldloc.0
0x25689  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x2568e  stloc.2
0x2568f  ldarg.0
0x25690  ldloc.2
0x25691  call     instance void System.Deployment.Application.Manifest.AssemblyManifest::LoadCMSFromStream(class [mscorlib]System.IO.Stream stream)
0x25696  leave.s  loc_256A2
0x25698  ldloc.2
0x25699  brfalse.s loc_256A1
0x2569b  ldloc.2
0x2569c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x256a1  endfinally
0x256a2  ldarg.0
0x256a3  ldarg.0
0x256a4  call     instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x256a9  callvirt instance object System.Deployment.Application.DefinitionIdentity::Clone()
0x256ae  castclass System.Deployment.Application.DefinitionIdentity
0x256b3  stfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::_id1Identity
0x256b8  ldarg.0
0x256b9  ldarg.0
0x256ba  call     instance string System.Deployment.Application.Manifest.AssemblyManifest::get_RequestedExecutionLevel()
0x256bf  stfld    string System.Deployment.Application.Manifest.AssemblyManifest::_id1RequestedExecutionLevel
0x256c4  ldstr    aId1identity// "_id1Identity = "
0x256c9  ldarg.0
0x256ca  ldfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::_id1Identity
0x256cf  brfalse.s loc_256DE
0x256d1  ldarg.0
0x256d2  ldfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::_id1Identity
0x256d7  callvirt instance string [mscorlib]System.Object::ToString()
0x256dc  br.s     loc_256E3
0x256de  ldstr    aNull// "null"
0x256e3  call     string [mscorlib]System.String::Concat(string, string)
0x256e8  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x256ed  ldarg.0
0x256ee  ldc.i4.2
0x256ef  stfld    valuetype System.Deployment.Application.Manifest.ManifestSourceFormat System.Deployment.Application.Manifest.AssemblyManifest::_manifestSourceFormat
0x256f4  ldc.i4.1
0x256f5  ret
0x256f6  ldstr    aFileDoesNotCon// "File does not contain ID_1 manifest."
0x256fb  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x25700  ldc.i4.0
0x25701  ret
```
