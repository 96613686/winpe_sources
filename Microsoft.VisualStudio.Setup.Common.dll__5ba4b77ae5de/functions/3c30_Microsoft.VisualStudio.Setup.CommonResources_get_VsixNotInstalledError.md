# Microsoft.VisualStudio.Setup.CommonResources::get_VsixNotInstalledError

- ea: `0x3c30`
- end: `0x3c45`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_VsixNotInstalledError`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x3c35`: `VsixNotInstalledError`

## pseudocode

```c

```

## disassembly

```asm
0x3c30  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x3c35  ldstr    aVsixnotinstall// "VsixNotInstalledError"
0x3c3a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x3c3f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3c44  ret
```
