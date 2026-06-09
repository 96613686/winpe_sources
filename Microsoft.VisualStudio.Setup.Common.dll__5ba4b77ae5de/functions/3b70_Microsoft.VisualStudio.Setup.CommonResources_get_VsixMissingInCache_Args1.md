# Microsoft.VisualStudio.Setup.CommonResources::get_VsixMissingInCache_Args1

- ea: `0x3b70`
- end: `0x3b85`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_VsixMissingInCache_Args1`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x3b75`: `VsixMissingInCache_Args1`

## pseudocode

```c

```

## disassembly

```asm
0x3b70  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x3b75  ldstr    aVsixmissinginc_0// "VsixMissingInCache_Args1"
0x3b7a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x3b7f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3b84  ret
```
