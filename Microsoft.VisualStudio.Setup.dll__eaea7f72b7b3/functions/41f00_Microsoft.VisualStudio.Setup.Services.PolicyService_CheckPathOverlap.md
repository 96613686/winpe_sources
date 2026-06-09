# Microsoft.VisualStudio.Setup.Services.PolicyService::CheckPathOverlap

- ea: `0x41f00`
- end: `0x41f79`
- name: `Microsoft.VisualStudio.Setup.Services.PolicyService::CheckPathOverlap`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x4f380`

## callees

- `0x199a0`
- `0x41f00`

## string_xrefs

- `0x41f68`: `PathOverlap_Cache_Shared`
- `0x41f17`: `PathOverlap_Installation_Cache`
- `0x41f3e`: `PathOverlap_Installation_Shared`

## pseudocode

```c

```

## disassembly

```asm
0x41f00  ldarg.0
0x41f01  ldarg.1
0x41f02  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::ContainsPath(string, string)
0x41f07  brtrue.s loc_41F12
0x41f09  ldarg.1
0x41f0a  ldarg.0
0x41f0b  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::ContainsPath(string, string)
0x41f10  brfalse.s loc_41F27
0x41f12  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x41f17  ldstr    aPathoverlapIns// "PathOverlap_Installation_Cache"
0x41f1c  call     T0x2B000003
0x41f21  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.EngineException::.ctor(class [mscorlib]System.Resources.ResourceManager, string, object[])
0x41f26  throw
0x41f27  ldarg.0
0x41f28  ldarg.2
0x41f29  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::ContainsPath(string, string)
0x41f2e  brtrue.s loc_41F39
0x41f30  ldarg.2
0x41f31  ldarg.0
0x41f32  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::ContainsPath(string, string)
0x41f37  brfalse.s loc_41F4E
0x41f39  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x41f3e  ldstr    aPathoverlapIns_0// "PathOverlap_Installation_Shared"
0x41f43  call     T0x2B000003
0x41f48  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.EngineException::.ctor(class [mscorlib]System.Resources.ResourceManager, string, object[])
0x41f4d  throw
0x41f4e  ldarg.3
0x41f4f  brfalse.s loc_41F78
0x41f51  ldarg.1
0x41f52  ldarg.2
0x41f53  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::ContainsPath(string, string)
0x41f58  brtrue.s loc_41F63
0x41f5a  ldarg.2
0x41f5b  ldarg.1
0x41f5c  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::ContainsPath(string, string)
0x41f61  brfalse.s loc_41F78
0x41f63  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x41f68  ldstr    aPathoverlapCac// "PathOverlap_Cache_Shared"
0x41f6d  call     T0x2B000003
0x41f72  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.EngineException::.ctor(class [mscorlib]System.Resources.ResourceManager, string, object[])
0x41f77  throw
0x41f78  ret
```
