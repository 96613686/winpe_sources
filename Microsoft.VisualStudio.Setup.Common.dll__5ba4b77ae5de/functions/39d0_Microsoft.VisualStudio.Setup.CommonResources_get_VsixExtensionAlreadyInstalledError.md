# Microsoft.VisualStudio.Setup.CommonResources::get_VsixExtensionAlreadyInstalledError

- ea: `0x39d0`
- end: `0x39e5`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_VsixExtensionAlreadyInstalledError`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x39d5`: `VsixExtensionAlreadyInstalledError`

## pseudocode

```c

```

## disassembly

```asm
0x39d0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x39d5  ldstr    aVsixextensiona// "VsixExtensionAlreadyInstalledError"
0x39da  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x39df  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x39e4  ret
```
