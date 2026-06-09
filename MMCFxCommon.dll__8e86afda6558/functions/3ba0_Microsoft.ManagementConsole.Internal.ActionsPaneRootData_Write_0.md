# Microsoft.ManagementConsole.Internal.ActionsPaneRootData::Write_0

- ea: `0x3ba0`
- end: `0x3cd4`
- name: `Microsoft.ManagementConsole.Internal.ActionsPaneRootData::Write_0`
- size: `308`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x3ac0`
- `0x3ba0`

## callees

- `0x3790`
- `0x37b0`
- `0x3820`
- `0x3840`
- `0x3870`
- `0x38b0`
- `0x38d0`
- `0x39e0`
- `0x3a00`
- `0x3a40`
- `0x3a60`
- `0x3ba0`

## pseudocode

```c

```

## disassembly

```asm
0x3ba0  ldarg.0
0x3ba1  ldfld    int32[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_id
0x3ba6  ldarg.2
0x3ba7  ldind.i4
0x3ba8  ldarg.1
0x3ba9  callvirt instance int32 Microsoft.ManagementConsole.Internal.ActionsPaneItemData::get_Id()
0x3bae  stelem.i4
0x3baf  ldarg.0
0x3bb0  ldfld    valuetype Microsoft.ManagementConsole.Internal.ActionsInsertionLocation[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_insertionLocation
0x3bb5  ldarg.2
0x3bb6  ldind.i4
0x3bb7  ldarg.1
0x3bb8  callvirt instance valuetype Microsoft.ManagementConsole.Internal.ActionsInsertionLocation Microsoft.ManagementConsole.Internal.ActionsPaneItemData::get_InsertionLocation()
0x3bbd  stelem.i4
0x3bbe  ldarg.0
0x3bbf  ldfld    valuetype Microsoft.ManagementConsole.Internal.ActionsPaneRootItemType[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_type
0x3bc4  ldarg.2
0x3bc5  ldind.i4
0x3bc6  ldc.i4.0
0x3bc7  stelem.i4
0x3bc8  ldarg.2
0x3bc9  dup
0x3bca  ldind.i4
0x3bcb  ldc.i4.1
0x3bcc  add
0x3bcd  stind.i4
0x3bce  ldarg.1
0x3bcf  isinst   Microsoft.ManagementConsole.Internal.ActionsPaneExtendedItemData
0x3bd4  stloc.0
0x3bd5  ldloc.0
0x3bd6  brfalse  loc_3CD3
0x3bdb  ldarg.0
0x3bdc  ldfld    string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_displayName
0x3be1  ldarg.3
0x3be2  ldind.i4
0x3be3  ldloc.0
0x3be4  callvirt instance string Microsoft.ManagementConsole.Internal.ActionsPaneExtendedItemData::get_DisplayName()
0x3be9  stelem.ref
0x3bea  ldarg.0
0x3beb  ldfld    string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_description
0x3bf0  ldarg.3
0x3bf1  ldind.i4
0x3bf2  ldloc.0
0x3bf3  callvirt instance string Microsoft.ManagementConsole.Internal.ActionsPaneExtendedItemData::get_Description()
0x3bf8  stelem.ref
0x3bf9  ldarg.0
0x3bfa  ldfld    string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_mnemonicDisplayName
0x3bff  ldarg.3
0x3c00  ldind.i4
0x3c01  ldloc.0
0x3c02  callvirt instance string Microsoft.ManagementConsole.Internal.ActionsPaneExtendedItemData::get_MnemonicDisplayName()
0x3c07  stelem.ref
0x3c08  ldarg.0
0x3c09  ldfld    string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_languageIndependentName
0x3c0e  ldarg.3
0x3c0f  ldind.i4
0x3c10  ldloc.0
0x3c11  callvirt instance string Microsoft.ManagementConsole.Internal.ActionsPaneExtendedItemData::get_LanguageIndependentName()
0x3c16  stelem.ref
0x3c17  ldarg.0
0x3c18  ldfld    int32[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_imageIndex
0x3c1d  ldarg.3
0x3c1e  ldind.i4
0x3c1f  ldloc.0
0x3c20  callvirt instance int32 Microsoft.ManagementConsole.Internal.ActionsPaneExtendedItemData::get_ImageIndex()
0x3c25  stelem.i4
0x3c26  ldarg.3
0x3c27  dup
0x3c28  ldind.i4
0x3c29  ldc.i4.1
0x3c2a  add
0x3c2b  stind.i4
0x3c2c  ldloc.0
0x3c2d  isinst   Microsoft.ManagementConsole.Internal.ActionData
0x3c32  stloc.1
0x3c33  ldloc.1
0x3c34  brfalse.s loc_3C6A
0x3c36  ldarg.0
0x3c37  ldfld    valuetype Microsoft.ManagementConsole.Internal.ActionStates[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_state
0x3c3c  ldarg.s  4
0x3c3e  ldind.i4
0x3c3f  ldloc.1
0x3c40  callvirt instance valuetype Microsoft.ManagementConsole.Internal.ActionStates Microsoft.ManagementConsole.Internal.ActionData::get_State()
0x3c45  stelem.i4
0x3c46  ldarg.0
0x3c47  ldfld    bool[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_executeSync
0x3c4c  ldarg.s  4
0x3c4e  ldind.i4
0x3c4f  ldloc.1
0x3c50  callvirt instance bool Microsoft.ManagementConsole.Internal.ActionData::get_ExecuteSync()
0x3c55  stelem.i1
0x3c56  ldarg.0
0x3c57  ldfld    valuetype Microsoft.ManagementConsole.Internal.ActionsPaneRootItemType[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_type
0x3c5c  ldarg.2
0x3c5d  ldind.i4
0x3c5e  ldc.i4.1
0x3c5f  sub
0x3c60  ldc.i4.1
0x3c61  stelem.i4
0x3c62  ldarg.s  4
0x3c64  dup
0x3c65  ldind.i4
0x3c66  ldc.i4.1
0x3c67  add
0x3c68  stind.i4
0x3c69  ret
0x3c6a  ldloc.0
0x3c6b  castclass Microsoft.ManagementConsole.Internal.ActionsPaneItemCollectionData
0x3c70  stloc.2
0x3c71  ldarg.0
0x3c72  ldfld    valuetype Microsoft.ManagementConsole.Internal.ActionsPaneRootItemType[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_type
0x3c77  ldarg.2
0x3c78  ldind.i4
0x3c79  ldc.i4.1
0x3c7a  sub
0x3c7b  ldc.i4.2
0x3c7c  stelem.i4
0x3c7d  ldarg.0
0x3c7e  ldfld    bool[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_renderAsRegion
0x3c83  ldarg.s  5
0x3c85  ldind.i4
0x3c86  ldloc.2
0x3c87  callvirt instance bool Microsoft.ManagementConsole.Internal.ActionsPaneItemCollectionData::get_RenderAsRegion()
0x3c8c  stelem.i1
0x3c8d  ldc.i4.0
0x3c8e  stloc.3
0x3c8f  ldloc.2
0x3c90  callvirt instance class Microsoft.ManagementConsole.Internal.ActionsPaneItemData[] Microsoft.ManagementConsole.Internal.ActionsPaneItemCollectionData::GetItems()
0x3c95  stloc.s  4
0x3c97  ldloc.s  4
0x3c99  brfalse.s loc_3CA0
0x3c9b  ldloc.s  4
0x3c9d  ldlen
0x3c9e  conv.i4
0x3c9f  stloc.3
0x3ca0  ldarg.0
0x3ca1  ldfld    int32[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_itemsCount
0x3ca6  ldarg.s  5
0x3ca8  ldind.i4
0x3ca9  ldloc.3
0x3caa  stelem.i4
0x3cab  ldarg.s  5
0x3cad  dup
0x3cae  ldind.i4
0x3caf  ldc.i4.1
0x3cb0  add
0x3cb1  stind.i4
0x3cb2  ldc.i4.0
0x3cb3  stloc.s  5
0x3cb5  br.s     loc_3CCE
0x3cb7  ldarg.0
0x3cb8  ldloc.s  4
0x3cba  ldloc.s  5
0x3cbc  ldelem.ref
0x3cbd  ldarg.2
0x3cbe  ldarg.3
0x3cbf  ldarg.s  4
0x3cc1  ldarg.s  5
0x3cc3  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::Write(class Microsoft.ManagementConsole.Internal.ActionsPaneItemData data, int32& index, int32& exItemIndex, int32& actionIndex, int32& colIndex)
0x3cc8  ldloc.s  5
0x3cca  ldc.i4.1
0x3ccb  add
0x3ccc  stloc.s  5
0x3cce  ldloc.s  5
0x3cd0  ldloc.3
0x3cd1  blt.s    loc_3CB7
0x3cd3  ret
```
