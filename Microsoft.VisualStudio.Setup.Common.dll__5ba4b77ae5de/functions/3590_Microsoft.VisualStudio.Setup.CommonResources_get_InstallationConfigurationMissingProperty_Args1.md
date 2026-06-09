# Microsoft.VisualStudio.Setup.CommonResources::get_InstallationConfigurationMissingProperty_Args1

- ea: `0x3590`
- end: `0x35a5`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_InstallationConfigurationMissingProperty_Args1`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x3595`: `InstallationConfigurationMissingProperty_Args1`

## pseudocode

```c

```

## disassembly

```asm
0x3590  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x3595  ldstr    aInstallationco// "InstallationConfigurationMissingPropert"...
0x359a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x359f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x35a4  ret
```
