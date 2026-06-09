# Microsoft.VisualStudio.Setup.CommonResources::get_PackageNoInstall

- ea: `0x3770`
- end: `0x3785`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_PackageNoInstall`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x3775`: `PackageNoInstall`

## pseudocode

```c

```

## disassembly

```asm
0x3770  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x3775  ldstr    aPackagenoinsta// "PackageNoInstall"
0x377a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x377f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3784  ret
```
