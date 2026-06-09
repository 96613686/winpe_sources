# Microsoft.ManagementConsole.SelectionData::Update

- ea: `0xd610`
- end: `0xd6ae`
- name: `Microsoft.ManagementConsole.SelectionData::Update`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1c0`
- `0x1d0`
- `0x62d0`
- `0x8440`
- `0xcbc0`
- `0xcc10`
- `0xd610`
- `0xd7e0`
- `0xd950`

## string_xrefs

- `0xd611`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0xd610  ldarg.0
0xd611  ldstr    aUpdate// "Update"
0xd616  call     instance void Microsoft.ManagementConsole.SelectionData::ThrowIfViewShutdown(string viewOperation)
0xd61b  ldarg.0
0xd61c  ldfld    class Microsoft.ManagementConsole.View Microsoft.ManagementConsole.SelectionData::_view
0xd621  isinst   Microsoft.ManagementConsole.MmcListView
0xd626  stloc.0
0xd627  ldloc.0
0xd628  brfalse.s loc_D679
0xd62a  ldloc.0
0xd62b  callvirt instance bool Microsoft.ManagementConsole.MmcListView::get_SnapInProcessingSelectionChange()
0xd630  brtrue.s loc_D642
0xd632  call     string Microsoft.ManagementConsole.Internal.Strings::get_SelectionDataUpdateInvalidFromList()
0xd637  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0xd63c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xd641  throw
0xd642  ldarg.2
0xd643  brfalse.s loc_D653
0xd645  ldloc.0
0xd646  callvirt instance class Microsoft.ManagementConsole.SelectedNodeCollection Microsoft.ManagementConsole.MmcListView::get_SelectedNodes()
0xd64b  callvirt instance int32 Microsoft.ManagementConsole.SelectedNodeCollection::get_Count()
0xd650  ldc.i4.2
0xd651  blt.s    loc_D664
0xd653  ldarg.2
0xd654  brtrue.s loc_D679
0xd656  ldloc.0
0xd657  callvirt instance class Microsoft.ManagementConsole.SelectedNodeCollection Microsoft.ManagementConsole.MmcListView::get_SelectedNodes()
0xd65c  callvirt instance int32 Microsoft.ManagementConsole.SelectedNodeCollection::get_Count()
0xd661  ldc.i4.1
0xd662  beq.s    loc_D679
0xd664  call     string Microsoft.ManagementConsole.Internal.Strings::get_SelectionDataUpdateInvalidUpdate()
0xd669  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0xd66e  ldstr    aMultiselection// "multiSelection"
0xd673  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xd678  throw
0xd679  ldarg.3
0xd67a  brfalse.s loc_D681
0xd67c  ldarg.3
0xd67d  ldlen
0xd67e  conv.i4
0xd67f  brtrue.s loc_D69C
0xd681  ldc.i4.1
0xd682  newarr   [mscorlib]System.Guid
0xd687  stloc.1
0xd688  ldloc.1
0xd689  ldc.i4.0
0xd68a  ldelema  [mscorlib]System.Guid
0xd68f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd694  stobj    [mscorlib]System.Guid
0xd699  ldloc.1
0xd69a  starg.s  3
0xd69c  ldarg.0
0xd69d  ldarg.1
0xd69e  ldarg.2
0xd69f  brtrue.s loc_D6A4
0xd6a1  ldc.i4.1
0xd6a2  br.s     loc_D6A5
0xd6a4  ldc.i4.2
0xd6a5  ldarg.3
0xd6a6  ldarg.s  4
0xd6a8  call     instance void Microsoft.ManagementConsole.SelectionData::ChangeSelection(object selectionObject, valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.SelectionCardinality type, valuetype [mscorlib]System.Guid[] uniqueNodeTypes, class Microsoft.ManagementConsole.WritableSharedData sharedData)
0xd6ad  ret
```
