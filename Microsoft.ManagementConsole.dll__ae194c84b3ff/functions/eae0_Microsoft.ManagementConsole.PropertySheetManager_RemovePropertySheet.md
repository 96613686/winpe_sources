# Microsoft.ManagementConsole.PropertySheetManager::RemovePropertySheet

- ea: `0xeae0`
- end: `0xeb21`
- name: `Microsoft.ManagementConsole.PropertySheetManager::RemovePropertySheet`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xe8f0`

## callees

- `0xdc10`
- `0xdc30`
- `0xe440`
- `0xe450`
- `0xea40`
- `0xeae0`

## pseudocode

```c

```

## disassembly

```asm
0xeae0  ldarg.1
0xeae1  brtrue.s loc_EAEE
0xeae3  ldstr    aSheet// "sheet"
0xeae8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xeaed  throw
0xeaee  ldarg.0
0xeaef  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ManagementConsole.PropertySheet> Microsoft.ManagementConsole.PropertySheetManager::_sheets
0xeaf4  ldarg.1
0xeaf5  callvirt instance int32 Microsoft.ManagementConsole.PropertySheet::get_Id()
0xeafa  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ManagementConsole.PropertySheet>::Remove(var<u1>)
0xeaff  pop
0xeb00  ldarg.1
0xeb01  callvirt instance class Microsoft.ManagementConsole.AuxiliarySelectionData Microsoft.ManagementConsole.PropertySheet::get_AuxiliarySelectionData()
0xeb06  stloc.0
0xeb07  ldloc.0
0xeb08  brfalse.s loc_EB20
0xeb0a  ldarg.0
0xeb0b  call     instance class Microsoft.ManagementConsole.AuxiliarySelectionDataCollection Microsoft.ManagementConsole.PropertySheetManager::get_ActiveViewPropertySheetSelectionDatas()
0xeb10  ldloc.0
0xeb11  callvirt instance int32 Microsoft.ManagementConsole.AuxiliarySelectionData::get_Id()
0xeb16  box      [mscorlib]System.Int32
0xeb1b  callvirt instance void Microsoft.ManagementConsole.AuxiliarySelectionDataCollection::Remove(object key)
0xeb20  ret
```
