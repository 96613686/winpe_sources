# Microsoft.VisualStudio.Setup.CommonResources::get_VsixInvalidExtensionPackageError

- ea: `0x3af0`
- end: `0x3b05`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_VsixInvalidExtensionPackageError`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x3af5`: `VsixInvalidExtensionPackageError`

## pseudocode

```c

```

## disassembly

```asm
0x3af0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x3af5  ldstr    aVsixinvalidext// "VsixInvalidExtensionPackageError"
0x3afa  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x3aff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3b04  ret
```
