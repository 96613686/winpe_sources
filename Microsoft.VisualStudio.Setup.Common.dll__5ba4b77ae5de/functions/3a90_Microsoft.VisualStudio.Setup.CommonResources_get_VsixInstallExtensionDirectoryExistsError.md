# Microsoft.VisualStudio.Setup.CommonResources::get_VsixInstallExtensionDirectoryExistsError

- ea: `0x3a90`
- end: `0x3aa5`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_VsixInstallExtensionDirectoryExistsError`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x3a95`: `VsixInstallExtensionDirectoryExistsError`

## pseudocode

```c

```

## disassembly

```asm
0x3a90  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x3a95  ldstr    aVsixinstallext// "VsixInstallExtensionDirectoryExistsErro"...
0x3a9a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x3a9f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3aa4  ret
```
