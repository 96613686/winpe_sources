# System.Deployment.Application.Manifest.AssemblyManifest::get_Identity

- ea: `0x24970`
- end: `0x249c2`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::get_Identity`
- size: `82`
- prototype: ``
- caller_count: `36`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0xb4c0`
- `0xb830`
- `0xba90`
- `0xd120`
- `0xd200`
- `0xf380`
- `0x105d0`
- `0x10650`
- `0x113b0`
- `0x11860`
- `0x13510`
- `0x13950`
- `0x139e0`
- `0x13d80`
- `0x17910`
- `0x17960`
- `0x179b0`
- `0x17a00`
- `0x18f40`
- `0x1ba20`
- `0x1e580`
- `0x1ecb0`
- `0x1efe0`
- `0x1f1c0`
- `0x1f8f0`
- `0x1f9c0`
- `0x1fda0`
- `0x1fe20`
- `0x20220`
- `0x25670`
- `0x25760`
- `0x25870`
- `0x25a00`
- `0x25bc0`
- `0x26250`
- `0x26d30`

## callees

- `0x4020`
- `0xd910`
- `0xd950`
- `0x24970`

## pseudocode

```c

```

## disassembly

```asm
0x24970  ldarg.0
0x24971  ldfld    object System.Deployment.Application.Manifest.AssemblyManifest::_identity
0x24976  brtrue.s loc_249B6
0x24978  ldarg.0
0x24979  ldfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x2497e  brfalse.s loc_249B6
0x24980  ldnull
0x24981  stloc.0
0x24982  ldarg.0
0x24983  ldfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x24988  callvirt instance class System.Deployment.Internal.Isolation.IDefinitionIdentity System.Deployment.Internal.Isolation.Manifest.ICMS::get_Identity()
0x2498d  brtrue.s loc_24997
0x2498f  newobj   instance void System.Deployment.Application.DefinitionIdentity::.ctor()
0x24994  stloc.0
0x24995  br.s     loc_249A8
0x24997  ldarg.0
0x24998  ldfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x2499d  callvirt instance class System.Deployment.Internal.Isolation.IDefinitionIdentity System.Deployment.Internal.Isolation.Manifest.ICMS::get_Identity()
0x249a2  newobj   instance void System.Deployment.Application.DefinitionIdentity::.ctor(class System.Deployment.Internal.Isolation.IDefinitionIdentity idComPtr)
0x249a7  stloc.0
0x249a8  ldarg.0
0x249a9  ldflda   object System.Deployment.Application.Manifest.AssemblyManifest::_identity
0x249ae  ldloc.0
0x249af  ldnull
0x249b0  call     object [mscorlib]System.Threading.Interlocked::CompareExchange(object&, object, object)
0x249b5  pop
0x249b6  ldarg.0
0x249b7  ldfld    object System.Deployment.Application.Manifest.AssemblyManifest::_identity
0x249bc  castclass System.Deployment.Application.DefinitionIdentity
0x249c1  ret
```
