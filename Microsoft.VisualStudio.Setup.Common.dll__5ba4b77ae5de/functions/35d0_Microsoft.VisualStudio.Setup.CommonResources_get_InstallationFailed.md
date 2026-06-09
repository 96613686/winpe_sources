# Microsoft.VisualStudio.Setup.CommonResources::get_InstallationFailed

- ea: `0x35d0`
- end: `0x35e5`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_InstallationFailed`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x35d5`: `InstallationFailed`

## pseudocode

```c

```

## disassembly

```asm
0x35d0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x35d5  ldstr    aInstallationfa// "InstallationFailed"
0x35da  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x35df  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x35e4  ret
```
