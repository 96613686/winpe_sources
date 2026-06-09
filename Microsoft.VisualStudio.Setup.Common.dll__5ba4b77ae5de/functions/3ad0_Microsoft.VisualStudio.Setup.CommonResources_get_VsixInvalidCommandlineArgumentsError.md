# Microsoft.VisualStudio.Setup.CommonResources::get_VsixInvalidCommandlineArgumentsError

- ea: `0x3ad0`
- end: `0x3ae5`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_VsixInvalidCommandlineArgumentsError`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x3ad5`: `VsixInvalidCommandlineArgumentsError`

## pseudocode

```c

```

## disassembly

```asm
0x3ad0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x3ad5  ldstr    aVsixinvalidcom// "VsixInvalidCommandlineArgumentsError"
0x3ada  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x3adf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3ae4  ret
```
