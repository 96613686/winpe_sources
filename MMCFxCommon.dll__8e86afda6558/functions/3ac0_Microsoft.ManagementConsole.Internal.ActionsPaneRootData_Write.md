# Microsoft.ManagementConsole.Internal.ActionsPaneRootData::Write

- ea: `0x3ac0`
- end: `0x3b9d`
- name: `Microsoft.ManagementConsole.Internal.ActionsPaneRootData::Write`
- size: `221`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x3ac0`
- `0x3ba0`
- `0x3f00`

## pseudocode

```c

```

## disassembly

```asm
0x3ac0  ldarg.1
0x3ac1  brtrue.s loc_3ACE
0x3ac3  ldstr    aData// "data"
0x3ac8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3acd  throw
0x3ace  ldc.i4.0
0x3acf  stloc.0
0x3ad0  ldc.i4.0
0x3ad1  stloc.1
0x3ad2  ldc.i4.0
0x3ad3  stloc.2
0x3ad4  ldarg.0
0x3ad5  ldarg.1
0x3ad6  ldloca.s 0
0x3ad8  ldloca.s 1
0x3ada  ldloca.s 2
0x3adc  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::CountItems(class Microsoft.ManagementConsole.Internal.ActionsPaneItemData data, int32& sepCount, int32& actionCount, int32& colCount)
0x3ae1  ldloc.0
0x3ae2  ldloc.1
0x3ae3  add
0x3ae4  ldloc.2
0x3ae5  add
0x3ae6  stloc.3
0x3ae7  ldloc.1
0x3ae8  ldloc.2
0x3ae9  add
0x3aea  stloc.s  4
0x3aec  ldarg.0
0x3aed  ldloc.3
0x3aee  newarr   [mscorlib]System.Int32
0x3af3  stfld    int32[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_id
0x3af8  ldarg.0
0x3af9  ldloc.3
0x3afa  newarr   Microsoft.ManagementConsole.Internal.ActionsPaneRootItemType
0x3aff  stfld    valuetype Microsoft.ManagementConsole.Internal.ActionsPaneRootItemType[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_type
0x3b04  ldarg.0
0x3b05  ldloc.3
0x3b06  newarr   Microsoft.ManagementConsole.Internal.ActionsInsertionLocation
0x3b0b  stfld    valuetype Microsoft.ManagementConsole.Internal.ActionsInsertionLocation[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_insertionLocation
0x3b10  ldarg.0
0x3b11  ldloc.s  4
0x3b13  newarr   [mscorlib]System.String
0x3b18  stfld    string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_displayName
0x3b1d  ldarg.0
0x3b1e  ldloc.s  4
0x3b20  newarr   [mscorlib]System.String
0x3b25  stfld    string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_description
0x3b2a  ldarg.0
0x3b2b  ldloc.s  4
0x3b2d  newarr   [mscorlib]System.String
0x3b32  stfld    string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_mnemonicDisplayName
0x3b37  ldarg.0
0x3b38  ldloc.s  4
0x3b3a  newarr   [mscorlib]System.String
0x3b3f  stfld    string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_languageIndependentName
0x3b44  ldarg.0
0x3b45  ldloc.s  4
0x3b47  newarr   [mscorlib]System.Int32
0x3b4c  stfld    int32[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_imageIndex
0x3b51  ldarg.0
0x3b52  ldloc.1
0x3b53  newarr   Microsoft.ManagementConsole.Internal.ActionStates
0x3b58  stfld    valuetype Microsoft.ManagementConsole.Internal.ActionStates[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_state
0x3b5d  ldarg.0
0x3b5e  ldloc.1
0x3b5f  newarr   [mscorlib]System.Boolean
0x3b64  stfld    bool[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_executeSync
0x3b69  ldarg.0
0x3b6a  ldloc.2
0x3b6b  newarr   [mscorlib]System.Boolean
0x3b70  stfld    bool[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_renderAsRegion
0x3b75  ldarg.0
0x3b76  ldloc.2
0x3b77  newarr   [mscorlib]System.Int32
0x3b7c  stfld    int32[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_itemsCount
0x3b81  ldc.i4.0
0x3b82  stloc.s  5
0x3b84  ldc.i4.0
0x3b85  stloc.s  6
0x3b87  ldc.i4.0
0x3b88  stloc.s  7
0x3b8a  ldc.i4.0
0x3b8b  stloc.s  8
0x3b8d  ldarg.0
0x3b8e  ldarg.1
0x3b8f  ldloca.s 5
0x3b91  ldloca.s 6
0x3b93  ldloca.s 7
0x3b95  ldloca.s 8
0x3b97  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::Write(class Microsoft.ManagementConsole.Internal.ActionsPaneItemData data, int32& index, int32& exItemIndex, int32& actionIndex, int32& colIndex)
0x3b9c  ret
```
