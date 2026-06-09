# System.Deployment.Application.CompatibleFrameworks::.ctor

- ea: `0xdf30`
- end: `0xdf54`
- name: `System.Deployment.Application.CompatibleFrameworks::.ctor`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x24e90`

## callees

- `0x27350`

## string_xrefs

- `0xdf3d`: `Ex_CompatibleFrameworksSupportUrlNotValid`

## pseudocode

```c

```

## disassembly

```asm
0xdf30  ldarg.0
0xdf31  call     instance void [mscorlib]System.Object::.ctor()
0xdf36  ldarg.0
0xdf37  ldarg.1
0xdf38  ldfld    string System.Deployment.Internal.Isolation.Manifest.CompatibleFrameworksMetadataEntry::SupportUrl
0xdf3d  ldstr    aExCompatiblefr// "Ex_CompatibleFrameworksSupportUrlNotVal"...
0xdf42  call     class [System]System.Uri System.Deployment.Application.Manifest.AssemblyManifest::UriFromMetadataEntry(string uriString, string exResourceStr)
0xdf47  stfld    class [System]System.Uri System.Deployment.Application.CompatibleFrameworks::_supportUrl
0xdf4c  ldarg.0
0xdf4d  ldarg.2
0xdf4e  stfld    class System.Deployment.Application.CompatibleFramework[] System.Deployment.Application.CompatibleFrameworks::_frameworks
0xdf53  ret
```
