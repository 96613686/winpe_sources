# System.Deployment.Application.ManifestGenerator::GenerateManifest

- ea: `0x18f40`
- end: `0x18fc3`
- name: `System.Deployment.Application.ManifestGenerator::GenerateManifest`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0xf380`

## callees

- `0xd960`
- `0x18f40`
- `0x19040`
- `0x190c0`
- `0x19180`
- `0x192a0`
- `0x24960`
- `0x24970`
- `0x24c50`
- `0x24dd0`

## pseudocode

```c

```

## disassembly

```asm
0x18f40  ldarg.1
0x18f41  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x18f46  stloc.0
0x18f47  ldarg.1
0x18f48  callvirt instance unsigned int8[] System.Deployment.Application.Manifest.AssemblyManifest::get_RawXmlBytes()
0x18f4d  brfalse.s loc_18F79
0x18f4f  ldarg.2
0x18f50  ldc.i4.1
0x18f51  ldc.i4.2
0x18f52  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::Open(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess)
0x18f57  stloc.1
0x18f58  ldloc.1
0x18f59  ldarg.1
0x18f5a  callvirt instance unsigned int8[] System.Deployment.Application.Manifest.AssemblyManifest::get_RawXmlBytes()
0x18f5f  ldc.i4.0
0x18f60  ldarg.1
0x18f61  callvirt instance unsigned int8[] System.Deployment.Application.Manifest.AssemblyManifest::get_RawXmlBytes()
0x18f66  ldlen
0x18f67  conv.i4
0x18f68  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x18f6d  leave.s  loc_18FC1
0x18f6f  ldloc.1
0x18f70  brfalse.s loc_18F78
0x18f72  ldloc.1
0x18f73  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18f78  endfinally
0x18f79  call     class [System.Xml]System.Xml.XmlDocument System.Deployment.Application.ManifestGenerator::CloneAssemblyTemplate()
0x18f7e  stloc.2
0x18f7f  ldarg.0
0x18f80  newobj   instance void System.Deployment.Application.DefinitionIdentity::.ctor(class System.Deployment.Application.ReferenceIdentity refId)
0x18f85  stloc.0
0x18f86  ldloc.2
0x18f87  ldloc.0
0x18f88  call     void System.Deployment.Application.ManifestGenerator::InjectIdentityXml(class [System.Xml]System.Xml.XmlDocument document, class System.Deployment.Application.DefinitionIdentity asmId)
0x18f8d  ldloc.2
0x18f8e  ldarg.1
0x18f8f  callvirt instance class System.Deployment.Application.Manifest.File[] System.Deployment.Application.Manifest.AssemblyManifest::get_Files()
0x18f94  call     void System.Deployment.Application.ManifestGenerator::AddFiles(class [System.Xml]System.Xml.XmlDocument document, class System.Deployment.Application.Manifest.File[] files)
0x18f99  ldloc.2
0x18f9a  ldarg.1
0x18f9b  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly[] System.Deployment.Application.Manifest.AssemblyManifest::get_DependentAssemblies()
0x18fa0  call     void System.Deployment.Application.ManifestGenerator::AddDependencies(class [System.Xml]System.Xml.XmlDocument document, class System.Deployment.Application.Manifest.DependentAssembly[] dependentAssemblies)
0x18fa5  ldarg.2
0x18fa6  ldc.i4.1
0x18fa7  ldc.i4.2
0x18fa8  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::Open(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess)
0x18fad  stloc.3
0x18fae  ldloc.2
0x18faf  ldloc.3
0x18fb0  callvirt instance void [System.Xml]System.Xml.XmlDocument::Save(class [mscorlib]System.IO.Stream)
0x18fb5  leave.s  loc_18FC1
0x18fb7  ldloc.3
0x18fb8  brfalse.s loc_18FC0
0x18fba  ldloc.3
0x18fbb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18fc0  endfinally
0x18fc1  ldloc.0
0x18fc2  ret
```
