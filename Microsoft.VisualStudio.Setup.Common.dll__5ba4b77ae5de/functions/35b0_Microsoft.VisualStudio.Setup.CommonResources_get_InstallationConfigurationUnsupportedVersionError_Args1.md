# Microsoft.VisualStudio.Setup.CommonResources::get_InstallationConfigurationUnsupportedVersionError_Args1

- ea: `0x35b0`
- end: `0x35c5`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_InstallationConfigurationUnsupportedVersionError_Args1`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x35b5`: `InstallationConfigurationUnsupportedVersionError_Args1`

## pseudocode

```c

```

## disassembly

```asm
0x35b0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x35b5  ldstr    aInstallationco_0// "InstallationConfigurationUnsupportedVer"...
0x35ba  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x35bf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x35c4  ret
```
