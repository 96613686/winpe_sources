# System.Deployment.Application.Manifest.AssemblyManifest::get_Description

- ea: `0x24b30`
- end: `0x24b81`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::get_Description`
- size: `81`
- prototype: ``
- caller_count: `19`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0xae50`
- `0xb170`
- `0xb2f0`
- `0xb4c0`
- `0xb6d0`
- `0xba90`
- `0xe080`
- `0x113b0`
- `0x12a70`
- `0x13fd0`
- `0x168a0`
- `0x1ba20`
- `0x1efa0`
- `0x1f550`
- `0x1f5f0`
- `0x1f680`
- `0x201e0`
- `0x25bc0`
- `0x26250`

## callees

- `0x40d0`
- `0x5020`
- `0x5400`
- `0x23b50`
- `0x24b30`

## pseudocode

```c

```

## disassembly

```asm
0x24b30  ldarg.0
0x24b31  ldfld    object System.Deployment.Application.Manifest.AssemblyManifest::_description
0x24b36  brtrue.s loc_24B75
0x24b38  ldarg.0
0x24b39  ldfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x24b3e  brfalse.s loc_24B75
0x24b40  ldarg.0
0x24b41  ldfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x24b46  callvirt instance class System.Deployment.Internal.Isolation.ISectionEntry System.Deployment.Internal.Isolation.Manifest.ICMS::get_MetadataSectionEntry()
0x24b4b  castclass System.Deployment.Internal.Isolation.Manifest.IMetadataSectionEntry
0x24b50  stloc.0
0x24b51  ldloc.0
0x24b52  callvirt instance class System.Deployment.Internal.Isolation.Manifest.IDescriptionMetadataEntry System.Deployment.Internal.Isolation.Manifest.IMetadataSectionEntry::get_DescriptionData()
0x24b57  stloc.1
0x24b58  ldloc.1
0x24b59  brfalse.s loc_24B75
0x24b5b  ldloc.1
0x24b5c  callvirt instance class System.Deployment.Internal.Isolation.Manifest.DescriptionMetadataEntry System.Deployment.Internal.Isolation.Manifest.IDescriptionMetadataEntry::get_AllData()
0x24b61  newobj   instance void System.Deployment.Application.Manifest.Description::.ctor(class System.Deployment.Internal.Isolation.Manifest.DescriptionMetadataEntry descriptionMetadataEntry)
0x24b66  stloc.2
0x24b67  ldarg.0
0x24b68  ldflda   object System.Deployment.Application.Manifest.AssemblyManifest::_description
0x24b6d  ldloc.2
0x24b6e  ldnull
0x24b6f  call     object [mscorlib]System.Threading.Interlocked::CompareExchange(object&, object, object)
0x24b74  pop
0x24b75  ldarg.0
0x24b76  ldfld    object System.Deployment.Application.Manifest.AssemblyManifest::_description
0x24b7b  castclass System.Deployment.Application.Manifest.Description
0x24b80  ret
```
