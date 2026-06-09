# Microsoft.VisualStudio.Setup.CommonResources::get_VsixMissingManifestError

- ea: `0x3b90`
- end: `0x3ba5`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_VsixMissingManifestError`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x3b95`: `VsixMissingManifestError`

## pseudocode

```c

```

## disassembly

```asm
0x3b90  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x3b95  ldstr    aVsixmissingman// "VsixMissingManifestError"
0x3b9a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x3b9f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3ba4  ret
```
