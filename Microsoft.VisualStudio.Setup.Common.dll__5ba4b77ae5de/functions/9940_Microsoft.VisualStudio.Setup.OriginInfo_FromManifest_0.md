# Microsoft.VisualStudio.Setup.OriginInfo::FromManifest_0

- ea: `0x9940`
- end: `0x9982`
- name: `Microsoft.VisualStudio.Setup.OriginInfo::FromManifest_0`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x2930`
- `0x9930`

## callees

- `0x5e80`
- `0x5fb0`
- `0x6020`
- `0x98c0`
- `0x98e0`
- `0x9900`
- `0x9920`
- `0x9990`
- `0xc1a0`

## string_xrefs

- `0x9941`: `manifest`

## pseudocode

```c

```

## disassembly

```asm
0x9940  ldarg.0
0x9941  ldstr    aManifest// "manifest"
0x9946  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x994b  newobj   instance void Microsoft.VisualStudio.Setup.OriginInfo::.ctor()
0x9950  dup
0x9951  ldarg.0
0x9952  call     string Microsoft.VisualStudio.Setup.Extensions::GetManifestId(class Microsoft.VisualStudio.Setup.IManifest manifest)
0x9957  callvirt instance void Microsoft.VisualStudio.Setup.OriginInfo::set_ManifestId(string value)
0x995c  dup
0x995d  ldarg.0
0x995e  call     string Microsoft.VisualStudio.Setup.Extensions::GetManifestName(class Microsoft.VisualStudio.Setup.IManifest manifest)
0x9963  callvirt instance void Microsoft.VisualStudio.Setup.OriginInfo::set_ManifestName(string value)
0x9968  dup
0x9969  ldarg.0
0x996a  ldarg.1
0x996b  call     T0x2B00000A
0x9970  callvirt instance void Microsoft.VisualStudio.Setup.OriginInfo::set_ManifestType(valuetype Microsoft.VisualStudio.Setup.PartialManifestType value)
0x9975  dup
0x9976  ldarg.0
0x9977  call     class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion(class Microsoft.VisualStudio.Setup.IManifest manifest)
0x997c  callvirt instance void Microsoft.VisualStudio.Setup.OriginInfo::set_ManifestBuildVersion(class [mscorlib]System.Version value)
0x9981  ret
```
