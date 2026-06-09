# System.Deployment.Application.Manifest.AssemblyManifest::LoadFromCompLibAssembly

- ea: `0x25760`
- end: `0x25867`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::LoadFromCompLibAssembly`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x25870`

## callees

- `0xdc90`
- `0xdce0`
- `0x19360`
- `0x19370`
- `0x193a0`
- `0x193c0`
- `0x19400`
- `0x19440`
- `0x19480`
- `0x23900`
- `0x24170`
- `0x24580`
- `0x245c0`
- `0x24970`
- `0x25760`

## pseudocode

```c

```

## disassembly

```asm
0x25760  ldarg.1
0x25761  newobj   instance void System.Deployment.Application.AssemblyMetaDataImport::.ctor(string sourceFile)
0x25766  stloc.0
0x25767  ldloc.0
0x25768  callvirt instance class [mscorlib]System.Reflection.AssemblyName System.Deployment.Application.AssemblyMetaDataImport::get_Name()
0x2576d  stloc.1
0x2576e  ldarg.0
0x2576f  ldarg.1
0x25770  call     class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Win32InterOp.SystemUtils::GetDefinitionIdentityFromManagedAssembly(string filePath)
0x25775  stfld    object System.Deployment.Application.Manifest.AssemblyManifest::_identity
0x2577a  ldarg.0
0x2577b  ldarg.0
0x2577c  call     instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x25781  callvirt instance object System.Deployment.Application.DefinitionIdentity::Clone()
0x25786  castclass System.Deployment.Application.DefinitionIdentity
0x2578b  stfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::_complibIdentity
0x25790  ldloc.0
0x25791  callvirt instance class System.Deployment.Application.AssemblyModule[] System.Deployment.Application.AssemblyMetaDataImport::get_Files()
0x25796  stloc.2
0x25797  ldloc.0
0x25798  callvirt instance class System.Deployment.Application.AssemblyReference[] System.Deployment.Application.AssemblyMetaDataImport::get_References()
0x2579d  stloc.3
0x2579e  ldloc.2
0x2579f  ldlen
0x257a0  conv.i4
0x257a1  ldc.i4.1
0x257a2  add
0x257a3  newarr   System.Deployment.Application.Manifest.File
0x257a8  stloc.s  4
0x257aa  ldloc.s  4
0x257ac  ldc.i4.0
0x257ad  ldarg.1
0x257ae  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x257b3  ldc.i4.0
0x257b4  conv.i8
0x257b5  newobj   instance void System.Deployment.Application.Manifest.File::.ctor(string name, unsigned int64 size)
0x257ba  stelem.ref
0x257bb  ldc.i4.0
0x257bc  stloc.s  6
0x257be  br.s     loc_257E6
0x257c0  ldloc.s  4
0x257c2  ldloc.s  6
0x257c4  ldc.i4.1
0x257c5  add
0x257c6  ldloc.2
0x257c7  ldloc.s  6
0x257c9  ldelem.ref
0x257ca  callvirt instance string System.Deployment.Application.AssemblyModule::get_Name()
0x257cf  ldloc.2
0x257d0  ldloc.s  6
0x257d2  ldelem.ref
0x257d3  callvirt instance unsigned int8[] System.Deployment.Application.AssemblyModule::get_Hash()
0x257d8  ldc.i4.0
0x257d9  conv.i8
0x257da  newobj   instance void System.Deployment.Application.Manifest.File::.ctor(string name, unsigned int8[] hash, unsigned int64 size)
0x257df  stelem.ref
0x257e0  ldloc.s  6
0x257e2  ldc.i4.1
0x257e3  add
0x257e4  stloc.s  6
0x257e6  ldloc.s  6
0x257e8  ldloc.2
0x257e9  ldlen
0x257ea  conv.i4
0x257eb  blt.s    loc_257C0
0x257ed  ldarg.0
0x257ee  ldloc.s  4
0x257f0  stfld    object System.Deployment.Application.Manifest.AssemblyManifest::_files
0x257f5  ldloc.3
0x257f6  ldlen
0x257f7  conv.i4
0x257f8  newarr   System.Deployment.Application.Manifest.DependentAssembly
0x257fd  stloc.s  5
0x257ff  ldc.i4.0
0x25800  stloc.s  7
0x25802  br.s     loc_25827
0x25804  ldloc.s  5
0x25806  ldloc.s  7
0x25808  ldloc.3
0x25809  ldloc.s  7
0x2580b  ldelem.ref
0x2580c  callvirt instance class [mscorlib]System.Reflection.AssemblyName System.Deployment.Application.AssemblyReference::get_Name()
0x25811  callvirt instance string [mscorlib]System.Object::ToString()
0x25816  newobj   instance void System.Deployment.Application.ReferenceIdentity::.ctor(string text)
0x2581b  newobj   instance void System.Deployment.Application.Manifest.DependentAssembly::.ctor(class System.Deployment.Application.ReferenceIdentity refId)
0x25820  stelem.ref
0x25821  ldloc.s  7
0x25823  ldc.i4.1
0x25824  add
0x25825  stloc.s  7
0x25827  ldloc.s  7
0x25829  ldloc.3
0x2582a  ldlen
0x2582b  conv.i4
0x2582c  blt.s    loc_25804
0x2582e  ldarg.0
0x2582f  ldloc.s  5
0x25831  stfld    object System.Deployment.Application.Manifest.AssemblyManifest::_dependentAssemblies
0x25836  ldarg.0
0x25837  ldc.i4.1
0x25838  stfld    valuetype System.Deployment.Application.Manifest.ManifestSourceFormat System.Deployment.Application.Manifest.AssemblyManifest::_manifestSourceFormat
0x2583d  ldc.i4.1
0x2583e  stloc.s  8
0x25840  leave.s  loc_25864
0x25842  ldloc.0
0x25843  brfalse.s loc_2584B
0x25845  ldloc.0
0x25846  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2584b  endfinally
0x2584c  pop
0x2584d  ldc.i4.0
0x2584e  stloc.s  8
0x25850  leave.s  loc_25864
0x25852  pop
0x25853  ldc.i4.0
0x25854  stloc.s  8
0x25856  leave.s  loc_25864
0x25858  pop
0x25859  ldc.i4.0
0x2585a  stloc.s  8
0x2585c  leave.s  loc_25864
0x2585e  pop
0x2585f  ldc.i4.0
0x25860  stloc.s  8
0x25862  leave.s  loc_25864
0x25864  ldloc.s  8
0x25866  ret
```
