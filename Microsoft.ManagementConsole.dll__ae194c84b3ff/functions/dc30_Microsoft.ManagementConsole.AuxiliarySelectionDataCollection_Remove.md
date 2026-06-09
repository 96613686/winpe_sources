# Microsoft.ManagementConsole.AuxiliarySelectionDataCollection::Remove

- ea: `0xdc30`
- end: `0xdc4e`
- name: `Microsoft.ManagementConsole.AuxiliarySelectionDataCollection::Remove`
- size: `30`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x9d20`
- `0xa5d0`
- `0xeae0`

## callees

- `0xdc30`

## pseudocode

```c

```

## disassembly

```asm
0xdc30  ldarg.0
0xdc31  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<object, class Microsoft.ManagementConsole.AuxiliarySelectionData> Microsoft.ManagementConsole.AuxiliarySelectionDataCollection::_selections
0xdc36  ldarg.1
0xdc37  ldloca.s 0
0xdc39  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<object, class Microsoft.ManagementConsole.AuxiliarySelectionData>::TryGetValue(var<u1>, !!T0)
0xdc3e  brfalse.s loc_DC4D
0xdc40  ldarg.0
0xdc41  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<object, class Microsoft.ManagementConsole.AuxiliarySelectionData> Microsoft.ManagementConsole.AuxiliarySelectionDataCollection::_selections
0xdc46  ldarg.1
0xdc47  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<object, class Microsoft.ManagementConsole.AuxiliarySelectionData>::Remove(var<u1>)
0xdc4c  pop
0xdc4d  ret
```
