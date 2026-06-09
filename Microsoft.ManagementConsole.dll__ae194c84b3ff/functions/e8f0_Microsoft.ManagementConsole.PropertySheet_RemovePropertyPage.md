# Microsoft.ManagementConsole.PropertySheet::RemovePropertyPage

- ea: `0xe8f0`
- end: `0xe930`
- name: `Microsoft.ManagementConsole.PropertySheet::RemovePropertyPage`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xe670`

## callees

- `0xe3c0`
- `0xe8f0`
- `0xeae0`

## pseudocode

```c

```

## disassembly

```asm
0xe8f0  ldarg.1
0xe8f1  brtrue.s loc_E8FE
0xe8f3  ldstr    aPropertypage// "propertyPage"
0xe8f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe8fd  throw
0xe8fe  ldarg.0
0xe8ff  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ManagementConsole.PropertyPage> Microsoft.ManagementConsole.PropertySheet::_pages
0xe904  ldarg.1
0xe905  callvirt instance int32 Microsoft.ManagementConsole.PropertyPage::get_Id()
0xe90a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ManagementConsole.PropertyPage>::Remove(var<u1>)
0xe90f  pop
0xe910  ldarg.0
0xe911  ldfld    int32 Microsoft.ManagementConsole.PropertySheet::_initPageCount
0xe916  brtrue.s loc_E92F
0xe918  ldarg.0
0xe919  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ManagementConsole.PropertyPage> Microsoft.ManagementConsole.PropertySheet::_pages
0xe91e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ManagementConsole.PropertyPage>::Clear()
0xe923  ldarg.0
0xe924  ldfld    class Microsoft.ManagementConsole.PropertySheetManager Microsoft.ManagementConsole.PropertySheet::_manager
0xe929  ldarg.0
0xe92a  callvirt instance void Microsoft.ManagementConsole.PropertySheetManager::RemovePropertySheet(class Microsoft.ManagementConsole.PropertySheet sheet)
0xe92f  ret
```
