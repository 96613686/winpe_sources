# Microsoft.VisualStudio.Setup.CommonResources::get_VsixInstallByMSIError

- ea: `0x3a50`
- end: `0x3a65`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_VsixInstallByMSIError`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x3a55`: `VsixInstallByMSIError`

## pseudocode

```c

```

## disassembly

```asm
0x3a50  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x3a55  ldstr    aVsixinstallbym// "VsixInstallByMSIError"
0x3a5a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x3a5f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3a64  ret
```
