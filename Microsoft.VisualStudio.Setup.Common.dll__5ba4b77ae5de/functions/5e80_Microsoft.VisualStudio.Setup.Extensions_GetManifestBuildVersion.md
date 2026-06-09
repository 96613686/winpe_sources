# Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion

- ea: `0x5e80`
- end: `0x5ea2`
- name: `Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion`
- size: `34`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x9940`
- `0x186b0`

## callees

- `0x5e80`
- `0x5f40`
- `0x6d30`
- `0xc1a0`

## string_xrefs

- `0x5e81`: `manifest`

## pseudocode

```c

```

## disassembly

```asm
0x5e80  ldarg.0
0x5e81  ldstr    aManifest// "manifest"
0x5e86  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x5e8b  ldarg.0
0x5e8c  callvirt instance class Microsoft.VisualStudio.Setup.CatalogInfo Microsoft.VisualStudio.Setup.IManifest::get_Info()
0x5e91  stloc.0
0x5e92  ldloc.0
0x5e93  brtrue.s loc_5E9B
0x5e95  ldsfld   class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Utilities::DefaultManifestVersion
0x5e9a  ret
0x5e9b  ldloc.0
0x5e9c  call     class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion(class Microsoft.VisualStudio.Setup.CatalogInfo info)
0x5ea1  ret
```
