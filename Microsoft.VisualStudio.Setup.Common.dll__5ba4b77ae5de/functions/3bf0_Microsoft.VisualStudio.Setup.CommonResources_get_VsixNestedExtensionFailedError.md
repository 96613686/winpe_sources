# Microsoft.VisualStudio.Setup.CommonResources::get_VsixNestedExtensionFailedError

- ea: `0x3bf0`
- end: `0x3c05`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_VsixNestedExtensionFailedError`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x3bf5`: `VsixNestedExtensionFailedError`

## pseudocode

```c

```

## disassembly

```asm
0x3bf0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x3bf5  ldstr    aVsixnestedexte// "VsixNestedExtensionFailedError"
0x3bfa  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x3bff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3c04  ret
```
