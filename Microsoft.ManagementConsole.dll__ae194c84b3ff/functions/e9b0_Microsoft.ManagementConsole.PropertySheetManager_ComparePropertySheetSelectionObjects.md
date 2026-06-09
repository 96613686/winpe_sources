# Microsoft.ManagementConsole.PropertySheetManager::ComparePropertySheetSelectionObjects

- ea: `0xe9b0`
- end: `0xe9e4`
- name: `Microsoft.ManagementConsole.PropertySheetManager::ComparePropertySheetSelectionObjects`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xa760`

## callees

- `0x83d0`
- `0xdc00`
- `0xdc50`
- `0xe9b0`
- `0xea40`

## pseudocode

```c

```

## disassembly

```asm
0xe9b0  ldc.i4.0
0xe9b1  stloc.0
0xe9b2  ldarg.1
0xe9b3  brtrue.s loc_E9C0
0xe9b5  ldstr    aSelectionobjec// "selectionObject"
0xe9ba  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe9bf  throw
0xe9c0  ldarg.0
0xe9c1  call     instance class Microsoft.ManagementConsole.AuxiliarySelectionDataCollection Microsoft.ManagementConsole.PropertySheetManager::get_ActiveViewPropertySheetSelectionDatas()
0xe9c6  ldarg.2
0xe9c7  box      [mscorlib]System.Int32
0xe9cc  callvirt instance class Microsoft.ManagementConsole.AuxiliarySelectionData Microsoft.ManagementConsole.AuxiliarySelectionDataCollection::get_Item(object key)
0xe9d1  stloc.1
0xe9d2  ldloc.1
0xe9d3  brfalse.s loc_E9E2
0xe9d5  ldarg.1
0xe9d6  ldloc.1
0xe9d7  callvirt instance object Microsoft.ManagementConsole.AuxiliarySelectionData::get_SelectionObject()
0xe9dc  call     bool Microsoft.ManagementConsole.Internal.Utility::CompareSelectionObjects(object selectionObjectA, object selectionObjectB)
0xe9e1  stloc.0
0xe9e2  ldloc.0
0xe9e3  ret
```
