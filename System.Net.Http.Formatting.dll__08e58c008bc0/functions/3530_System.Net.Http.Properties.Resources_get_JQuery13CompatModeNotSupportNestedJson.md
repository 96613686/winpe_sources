# System.Net.Http.Properties.Resources::get_JQuery13CompatModeNotSupportNestedJson

- ea: `0x3530`
- end: `0x3545`
- name: `System.Net.Http.Properties.Resources::get_JQuery13CompatModeNotSupportNestedJson`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6460`

## callees

- `0x30a0`

## string_xrefs

- `0x3535`: `JQuery13CompatModeNotSupportNestedJson`

## pseudocode

```c

```

## disassembly

```asm
0x3530  call     class [mscorlib]System.Resources.ResourceManager System.Net.Http.Properties.Resources::get_ResourceManager()
0x3535  ldstr    aJquery13compat// "JQuery13CompatModeNotSupportNestedJson"
0x353a  ldsfld   class [mscorlib]System.Globalization.CultureInfo System.Net.Http.Properties.Resources::resourceCulture
0x353f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3544  ret
```
