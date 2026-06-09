# Microsoft.VisualStudio.Setup.CommonResources::get_UninstallingDisplayText

- ea: `0x3830`
- end: `0x3845`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_UninstallingDisplayText`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x3835`: `UninstallingDisplayText`

## pseudocode

```c

```

## disassembly

```asm
0x3830  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x3835  ldstr    aUninstallingdi// "UninstallingDisplayText"
0x383a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x383f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3844  ret
```
