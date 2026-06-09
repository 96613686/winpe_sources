# Microsoft.VisualStudio.Setup.CommonResources::get_ValidateError_InvalidDirectoryPath_Args1

- ea: `0x3890`
- end: `0x38a5`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_ValidateError_InvalidDirectoryPath_Args1`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xc220`

## callees

- `0x3380`

## string_xrefs

- `0x3895`: `ValidateError_InvalidDirectoryPath_Args1`

## pseudocode

```c

```

## disassembly

```asm
0x3890  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x3895  ldstr    aValidateerrorI// "ValidateError_InvalidDirectoryPath_Args"...
0x389a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x389f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x38a4  ret
```
