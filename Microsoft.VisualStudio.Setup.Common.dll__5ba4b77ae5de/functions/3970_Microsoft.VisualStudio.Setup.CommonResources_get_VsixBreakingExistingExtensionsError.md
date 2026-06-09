# Microsoft.VisualStudio.Setup.CommonResources::get_VsixBreakingExistingExtensionsError

- ea: `0x3970`
- end: `0x3985`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_VsixBreakingExistingExtensionsError`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x3975`: `VsixBreakingExistingExtensionsError`

## pseudocode

```c

```

## disassembly

```asm
0x3970  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x3975  ldstr    aVsixbreakingex// "VsixBreakingExistingExtensionsError"
0x397a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x397f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3984  ret
```
