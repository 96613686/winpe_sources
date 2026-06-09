# Microsoft.VisualStudio.Setup.CommonResources::get_VsixInstallerNotFoundError

- ea: `0x3a70`
- end: `0x3a85`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_VsixInstallerNotFoundError`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x3a75`: `VsixInstallerNotFoundError`

## pseudocode

```c

```

## disassembly

```asm
0x3a70  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x3a75  ldstr    aVsixinstallern// "VsixInstallerNotFoundError"
0x3a7a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x3a7f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3a84  ret
```
