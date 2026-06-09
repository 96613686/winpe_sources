# Microsoft.VisualStudio.Setup.CommonResources::get_PackageNoRepair

- ea: `0x3790`
- end: `0x37a5`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_PackageNoRepair`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x3795`: `PackageNoRepair`

## pseudocode

```c

```

## disassembly

```asm
0x3790  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x3795  ldstr    aPackagenorepai// "PackageNoRepair"
0x379a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x379f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x37a4  ret
```
