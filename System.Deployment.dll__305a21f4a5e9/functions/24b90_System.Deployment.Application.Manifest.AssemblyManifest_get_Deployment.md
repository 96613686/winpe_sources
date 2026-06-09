# System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment

- ea: `0x24b90`
- end: `0x24be1`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment`
- size: `81`
- prototype: ``
- caller_count: `28`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0xae50`
- `0xb170`
- `0xb2f0`
- `0xb4c0`
- `0xb6d0`
- `0xba90`
- `0xc5b0`
- `0xd120`
- `0xe780`
- `0xef90`
- `0xf030`
- `0x113b0`
- `0x11b00`
- `0x11d60`
- `0x12190`
- `0x122a0`
- `0x13230`
- `0x13950`
- `0x139e0`
- `0x13d30`
- `0x162f0`
- `0x1dba0`
- `0x1fb50`
- `0x1fd60`
- `0x1fda0`
- `0x25bc0`
- `0x26250`
- `0x29ab0`

## callees

- `0x40d0`
- `0x50d0`
- `0x5410`
- `0x23ef0`
- `0x24b90`

## pseudocode

```c

```

## disassembly

```asm
0x24b90  ldarg.0
0x24b91  ldfld    object System.Deployment.Application.Manifest.AssemblyManifest::_deployment
0x24b96  brtrue.s loc_24BD5
0x24b98  ldarg.0
0x24b99  ldfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x24b9e  brfalse.s loc_24BD5
0x24ba0  ldarg.0
0x24ba1  ldfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x24ba6  callvirt instance class System.Deployment.Internal.Isolation.ISectionEntry System.Deployment.Internal.Isolation.Manifest.ICMS::get_MetadataSectionEntry()
0x24bab  castclass System.Deployment.Internal.Isolation.Manifest.IMetadataSectionEntry
0x24bb0  stloc.0
0x24bb1  ldloc.0
0x24bb2  callvirt instance class System.Deployment.Internal.Isolation.Manifest.IDeploymentMetadataEntry System.Deployment.Internal.Isolation.Manifest.IMetadataSectionEntry::get_DeploymentData()
0x24bb7  stloc.1
0x24bb8  ldloc.1
0x24bb9  brfalse.s loc_24BD5
0x24bbb  ldloc.1
0x24bbc  callvirt instance class System.Deployment.Internal.Isolation.Manifest.DeploymentMetadataEntry System.Deployment.Internal.Isolation.Manifest.IDeploymentMetadataEntry::get_AllData()
0x24bc1  newobj   instance void System.Deployment.Application.Manifest.Deployment::.ctor(class System.Deployment.Internal.Isolation.Manifest.DeploymentMetadataEntry deploymentMetadataEntry)
0x24bc6  stloc.2
0x24bc7  ldarg.0
0x24bc8  ldflda   object System.Deployment.Application.Manifest.AssemblyManifest::_deployment
0x24bcd  ldloc.2
0x24bce  ldnull
0x24bcf  call     object [mscorlib]System.Threading.Interlocked::CompareExchange(object&, object, object)
0x24bd4  pop
0x24bd5  ldarg.0
0x24bd6  ldfld    object System.Deployment.Application.Manifest.AssemblyManifest::_deployment
0x24bdb  castclass System.Deployment.Application.Manifest.Deployment
0x24be0  ret
```
