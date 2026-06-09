# Microsoft.VisualStudio.Setup.CommonResources::get_VsixUnsupportedManifestFormatError

- ea: `0x3cf0`
- end: `0x3d05`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_VsixUnsupportedManifestFormatError`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x3cf5`: `VsixUnsupportedManifestFormatError`

## pseudocode

```c

```

## disassembly

```asm
0x3cf0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x3cf5  ldstr    aVsixunsupporte// "VsixUnsupportedManifestFormatError"
0x3cfa  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x3cff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3d04  ret
```
