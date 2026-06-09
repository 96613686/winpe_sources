# Microsoft.VisualStudio.Setup.CommonResources::get_InstallingDisplayText

- ea: `0x35f0`
- end: `0x3605`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_InstallingDisplayText`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x35f5`: `InstallingDisplayText`

## pseudocode

```c

```

## disassembly

```asm
0x35f0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x35f5  ldstr    aInstallingdisp// "InstallingDisplayText"
0x35fa  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x35ff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3604  ret
```
