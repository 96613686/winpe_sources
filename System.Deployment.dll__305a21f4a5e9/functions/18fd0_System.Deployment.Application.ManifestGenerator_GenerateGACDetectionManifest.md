# System.Deployment.Application.ManifestGenerator::GenerateGACDetectionManifest

- ea: `0x18fd0`
- end: `0x19035`
- name: `System.Deployment.Application.ManifestGenerator::GenerateGACDetectionManifest`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1b9a0`

## callees

- `0xd930`
- `0x18fd0`
- `0x190c0`
- `0x19180`
- `0x192a0`
- `0x24170`

## string_xrefs

- `0x18fe2`: `GACDetectionTempManifest, version=1.0.0.0, type=win32`

## pseudocode

```c

```

## disassembly

```asm
0x18fd0  call     class [System.Xml]System.Xml.XmlDocument System.Deployment.Application.ManifestGenerator::CloneAssemblyTemplate()
0x18fd5  stloc.0
0x18fd6  ldsfld   object System.Deployment.Application.ManifestGenerator::GACDetectionTempManifestAsmId
0x18fdb  brtrue.s loc_18FF3
0x18fdd  ldsflda  object System.Deployment.Application.ManifestGenerator::GACDetectionTempManifestAsmId
0x18fe2  ldstr    aGacdetectionte// "GACDetectionTempManifest, version=1.0.0"...
0x18fe7  newobj   instance void System.Deployment.Application.DefinitionIdentity::.ctor(string text)
0x18fec  ldnull
0x18fed  call     object [mscorlib]System.Threading.Interlocked::CompareExchange(object&, object, object)
0x18ff2  pop
0x18ff3  ldloc.0
0x18ff4  ldsfld   object System.Deployment.Application.ManifestGenerator::GACDetectionTempManifestAsmId
0x18ff9  castclass System.Deployment.Application.DefinitionIdentity
0x18ffe  call     void System.Deployment.Application.ManifestGenerator::InjectIdentityXml(class [System.Xml]System.Xml.XmlDocument document, class System.Deployment.Application.DefinitionIdentity asmId)
0x19003  ldloc.0
0x19004  ldc.i4.1
0x19005  newarr   System.Deployment.Application.Manifest.DependentAssembly
0x1900a  dup
0x1900b  ldc.i4.0
0x1900c  ldarg.0
0x1900d  newobj   instance void System.Deployment.Application.Manifest.DependentAssembly::.ctor(class System.Deployment.Application.ReferenceIdentity refId)
0x19012  stelem.ref
0x19013  call     void System.Deployment.Application.ManifestGenerator::AddDependencies(class [System.Xml]System.Xml.XmlDocument document, class System.Deployment.Application.Manifest.DependentAssembly[] dependentAssemblies)
0x19018  ldarg.1
0x19019  ldc.i4.1
0x1901a  ldc.i4.2
0x1901b  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::Open(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess)
0x19020  stloc.1
0x19021  ldloc.0
0x19022  ldloc.1
0x19023  callvirt instance void [System.Xml]System.Xml.XmlDocument::Save(class [mscorlib]System.IO.Stream)
0x19028  leave.s  loc_19034
0x1902a  ldloc.1
0x1902b  brfalse.s loc_19033
0x1902d  ldloc.1
0x1902e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19033  endfinally
0x19034  ret
```
