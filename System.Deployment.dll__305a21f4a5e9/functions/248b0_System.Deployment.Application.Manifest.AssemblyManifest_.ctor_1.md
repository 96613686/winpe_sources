# System.Deployment.Application.Manifest.AssemblyManifest::.ctor_1

- ea: `0x248b0`
- end: `0x24916`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::.ctor_1`
- size: `102`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0xf380`
- `0x13820`
- `0x13d80`
- `0x15210`

## callees

- `0x248b0`
- `0x25630`
- `0x25870`
- `0x259d0`

## string_xrefs

- `0x248d5`: `.manifest`

## pseudocode

```c

```

## disassembly

```asm
0x248b0  ldarg.0
0x248b1  ldc.i4.4
0x248b2  stfld    valuetype System.Deployment.Application.Manifest.ManifestSourceFormat System.Deployment.Application.Manifest.AssemblyManifest::_manifestSourceFormat
0x248b7  ldarg.0
0x248b8  call     instance void [mscorlib]System.Object::.ctor()
0x248bd  ldarg.1
0x248be  call     string [mscorlib]System.IO.Path::GetExtension(string)
0x248c3  stloc.0
0x248c4  ldc.i4.3
0x248c5  stloc.1
0x248c6  ldloc.0
0x248c7  ldstr    aApplication// ".application"
0x248cc  ldloc.1
0x248cd  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x248d2  brtrue.s loc_248E2
0x248d4  ldloc.0
0x248d5  ldstr    aManifest// ".manifest"
0x248da  ldloc.1
0x248db  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x248e0  brfalse.s loc_248EA
0x248e2  ldarg.0
0x248e3  ldarg.1
0x248e4  call     instance void System.Deployment.Application.Manifest.AssemblyManifest::LoadFromRawXmlFile(string filePath)
0x248e9  ret
0x248ea  ldloc.0
0x248eb  ldstr    aDll// ".dll"
0x248f0  ldloc.1
0x248f1  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x248f6  brtrue.s loc_24906
0x248f8  ldloc.0
0x248f9  ldstr    aExe// ".exe"
0x248fe  ldloc.1
0x248ff  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x24904  brfalse.s loc_2490E
0x24906  ldarg.0
0x24907  ldarg.1
0x24908  call     instance void System.Deployment.Application.Manifest.AssemblyManifest::LoadFromInternalManifestFile(string filePath)
0x2490d  ret
0x2490e  ldarg.0
0x2490f  ldarg.1
0x24910  call     instance void System.Deployment.Application.Manifest.AssemblyManifest::LoadFromUnknownFormatFile(string filePath)
0x24915  ret
```
