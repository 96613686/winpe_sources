# Microsoft.VisualStudio.Setup.CommonResources::get_PackageNoUninstall

- ea: `0x37b0`
- end: `0x37c5`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_PackageNoUninstall`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x37b5`: `PackageNoUninstall`

## pseudocode

```c

```

## disassembly

```asm
0x37b0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x37b5  ldstr    aPackagenounins// "PackageNoUninstall"
0x37ba  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x37bf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x37c4  ret
```
