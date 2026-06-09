# Microsoft.Windows.ManagementUI.CombinedControls.Resources.MIGUICommon::get_ResourceManager

- ea: `0x96650`
- end: `0x9667b`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.Resources.MIGUICommon::get_ResourceManager`
- size: `43`
- prototype: ``
- caller_count: `796`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x12ed0`
- `0x966a0`
- `0x966c0`
- `0x966e0`
- `0x96700`
- `0x96720`
- `0x96740`
- `0x96760`
- `0x96780`
- `0x967a0`
- `0x967c0`
- `0x967e0`
- `0x96800`
- `0x96820`
- `0x96840`
- `0x96860`
- `0x96880`
- `0x968a0`
- `0x968c0`
- `0x968e0`
- `0x96900`
- `0x96920`
- `0x96940`
- `0x96960`
- `0x96980`
- `0x969a0`
- `0x969c0`
- `0x969e0`
- `0x96a00`
- `0x96a20`
- `0x96a40`
- `0x96a60`
- `0x96a80`
- `0x96aa0`
- `0x96ac0`
- `0x96ae0`
- `0x96b00`
- `0x96b20`
- `0x96b40`
- `0x96b60`
- `0x96b80`
- `0x96ba0`
- `0x96bc0`
- `0x96be0`
- `0x96c00`
- `0x96c20`
- `0x96c40`
- `0x96c60`
- `0x96c80`
- `0x96ca0`

## callees

- `0x96650`

## string_xrefs

- `0x96657`: `Microsoft.Windows.ManagementUI.CombinedControls.Resources.MIGUICommon`

## pseudocode

```c

```

## disassembly

```asm
0x96650  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Windows.ManagementUI.CombinedControls.Resources.MIGUICommon::resourceMan
0x96655  brtrue.s loc_96675
0x96657  ldstr    aMicrosoftWindo_4// "Microsoft.Windows.ManagementUI.Combined"...
0x9665c  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.Resources.MIGUICommon
0x96661  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x96666  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x9666b  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x96670  stsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Windows.ManagementUI.CombinedControls.Resources.MIGUICommon::resourceMan
0x96675  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.Windows.ManagementUI.CombinedControls.Resources.MIGUICommon::resourceMan
0x9667a  ret
```
