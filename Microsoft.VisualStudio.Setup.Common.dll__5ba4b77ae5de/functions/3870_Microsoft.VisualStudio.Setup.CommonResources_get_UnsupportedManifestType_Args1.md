# Microsoft.VisualStudio.Setup.CommonResources::get_UnsupportedManifestType_Args1

- ea: `0x3870`
- end: `0x3885`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_UnsupportedManifestType_Args1`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x6060`

## callees

- `0x3380`

## string_xrefs

- `0x3875`: `UnsupportedManifestType_Args1`

## pseudocode

```c

```

## disassembly

```asm
0x3870  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x3875  ldstr    aUnsupportedman// "UnsupportedManifestType_Args1"
0x387a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x387f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3884  ret
```
