# Microsoft.VisualStudio.Setup.WorkPrimaryProcess::GetCacheChannelManifestVersion

- ea: `0x34c0`
- end: `0x34de`
- name: `Microsoft.VisualStudio.Setup.WorkPrimaryProcess::GetCacheChannelManifestVersion`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x2fc0`

## pseudocode

```c

```

## disassembly

```asm
0x34c0  ldarg.1
0x34c1  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_UserProperties()
0x34c6  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.WellKnownPropertyNames::ChannelManifestBuildVersion
0x34cb  ldloca.s 0
0x34cd  callvirt instance bool class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x34d2  pop
0x34d3  ldloc.0
0x34d4  ldloca.s 1
0x34d6  call     bool [mscorlib]System.Version::TryParse(string, class [mscorlib]System.Version&)
0x34db  pop
0x34dc  ldloc.1
0x34dd  ret
```
