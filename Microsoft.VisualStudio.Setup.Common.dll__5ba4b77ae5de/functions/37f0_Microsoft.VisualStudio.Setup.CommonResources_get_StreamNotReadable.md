# Microsoft.VisualStudio.Setup.CommonResources::get_StreamNotReadable

- ea: `0x37f0`
- end: `0x3805`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_StreamNotReadable`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x37f5`: `StreamNotReadable`

## pseudocode

```c

```

## disassembly

```asm
0x37f0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x37f5  ldstr    aStreamnotreada// "StreamNotReadable"
0x37fa  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x37ff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3804  ret
```
