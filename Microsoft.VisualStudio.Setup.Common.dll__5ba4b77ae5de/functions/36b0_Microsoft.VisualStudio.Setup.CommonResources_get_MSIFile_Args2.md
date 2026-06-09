# Microsoft.VisualStudio.Setup.CommonResources::get_MSIFile_Args2

- ea: `0x36b0`
- end: `0x36c5`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_MSIFile_Args2`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x36b5`: `MSIFile_Args2`

## pseudocode

```c

```

## disassembly

```asm
0x36b0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x36b5  ldstr    aMsifileArgs2// "MSIFile_Args2"
0x36ba  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x36bf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x36c4  ret
```
