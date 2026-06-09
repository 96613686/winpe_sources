# Microsoft.VisualStudio.Setup.CommonResources::get_CommandExecuted_Args1

- ea: `0x3410`
- end: `0x3425`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_CommandExecuted_Args1`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3380`

## string_xrefs

- `0x3415`: `CommandExecuted_Args1`

## pseudocode

```c

```

## disassembly

```asm
0x3410  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager()
0x3415  ldstr    aCommandexecute// "CommandExecuted_Args1"
0x341a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.CommonResources::resourceCulture
0x341f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3424  ret
```
