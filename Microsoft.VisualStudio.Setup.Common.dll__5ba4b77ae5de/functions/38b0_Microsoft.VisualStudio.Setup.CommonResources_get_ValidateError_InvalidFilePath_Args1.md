# Microsoft.VisualStudio.Setup.CommonResources::get_ValidateError_InvalidFilePath_Args1

- ea: `0x38b0`
- end: `0x38c5`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_ValidateError_InvalidFilePath_Args1`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xc250`

## callees

- `0x3380`

## string_xrefs

- `0x38b5`: `ValidateError_InvalidFilePath_Args1`

## pseudocode

```c

```

## disassembly

```asm
0x38b0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x38b5  ldstr    aValidateerrorI_0// "ValidateError_InvalidFilePath_Args1"
0x38ba  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x38bf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x38c4  ret
```
