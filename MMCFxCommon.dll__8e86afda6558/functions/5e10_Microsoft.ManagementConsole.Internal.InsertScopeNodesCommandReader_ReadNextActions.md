# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextActions

- ea: `0x5e10`
- end: `0x627a`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextActions`
- size: `1130`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `broker_com_uri`

## callers

- `0x58d0`

## callees

- `0x3f60`
- `0x3f80`
- `0x3fa0`
- `0x3fc0`
- `0x3fe0`
- `0x4000`
- `0x4020`
- `0x4040`
- `0x4060`
- `0x4080`
- `0x40a0`
- `0x40c0`
- `0x5e10`
- `0x7c80`
- `0x7ca0`
- `0x7cc0`
- `0x7ce0`
- `0x7d00`
- `0x7d20`
- `0x7d40`
- `0x7d60`
- `0x7d80`
- `0x7da0`
- `0x7dc0`
- `0x7de0`
- `0x7e00`
- `0x7e20`
- `0x7e40`
- `0x7e60`
- `0x7e80`
- `0x7ea0`
- `0x7ec0`
- `0x7ee0`

## pseudocode

```c

```

## disassembly

```asm
0x5e10  ldloca.s 0
0x5e12  initobj  Microsoft.ManagementConsole.Internal.ActionsPaneRootData
0x5e18  ldarg.0
0x5e19  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5e1e  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_Actions_Id_Count()
0x5e23  ldarg.0
0x5e24  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5e29  ldelem.i4
0x5e2a  stloc.1
0x5e2b  ldnull
0x5e2c  stloc.2
0x5e2d  ldloc.1
0x5e2e  ldc.i4.0
0x5e2f  blt.s    loc_5E5F
0x5e31  ldloc.1
0x5e32  newarr   [mscorlib]System.Int32
0x5e37  stloc.2
0x5e38  ldarg.0
0x5e39  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5e3e  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_Actions_Id()
0x5e43  ldarg.0
0x5e44  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_Actions_Id_Offset
0x5e49  ldloc.2
0x5e4a  ldc.i4.0
0x5e4b  ldloc.1
0x5e4c  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x5e51  ldarg.0
0x5e52  ldarg.0
0x5e53  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_Actions_Id_Offset
0x5e58  ldloc.1
0x5e59  add
0x5e5a  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_Actions_Id_Offset
0x5e5f  ldloca.s 0
0x5e61  ldloc.2
0x5e62  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::SetId(int32[] value)
0x5e67  ldarg.0
0x5e68  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5e6d  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_Actions_ItemType_Count()
0x5e72  ldarg.0
0x5e73  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5e78  ldelem.i4
0x5e79  stloc.3
0x5e7a  ldnull
0x5e7b  stloc.s  4
0x5e7d  ldloc.3
0x5e7e  ldc.i4.0
0x5e7f  blt.s    loc_5E89
0x5e81  ldloc.3
0x5e82  newarr   Microsoft.ManagementConsole.Internal.ActionsPaneRootItemType
0x5e87  stloc.s  4
0x5e89  ldc.i4.0
0x5e8a  stloc.s  5
0x5e8c  ldc.i4.0
0x5e8d  stloc.s  5
0x5e8f  br.s     loc_5EBC
0x5e91  ldloc.s  4
0x5e93  ldloc.s  5
0x5e95  ldarg.0
0x5e96  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5e9b  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_Actions_ItemType()
0x5ea0  ldarg.0
0x5ea1  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_Actions_ItemType_Offset
0x5ea6  ldelem.i4
0x5ea7  stelem.i4
0x5ea8  ldarg.0
0x5ea9  ldarg.0
0x5eaa  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_Actions_ItemType_Offset
0x5eaf  ldc.i4.1
0x5eb0  add
0x5eb1  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_Actions_ItemType_Offset
0x5eb6  ldloc.s  5
0x5eb8  ldc.i4.1
0x5eb9  add
0x5eba  stloc.s  5
0x5ebc  ldloc.s  5
0x5ebe  ldloc.3
0x5ebf  blt.s    loc_5E91
0x5ec1  ldloca.s 0
0x5ec3  ldloc.s  4
0x5ec5  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::SetItemType(valuetype Microsoft.ManagementConsole.Internal.ActionsPaneRootItemType[] value)
0x5eca  ldarg.0
0x5ecb  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5ed0  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_Actions_InsertionLocation_Count()
0x5ed5  ldarg.0
0x5ed6  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5edb  ldelem.i4
0x5edc  stloc.s  6
0x5ede  ldnull
0x5edf  stloc.s  7
0x5ee1  ldloc.s  6
0x5ee3  ldc.i4.0
0x5ee4  blt.s    loc_5EEF
0x5ee6  ldloc.s  6
0x5ee8  newarr   Microsoft.ManagementConsole.Internal.ActionsInsertionLocation
0x5eed  stloc.s  7
0x5eef  ldc.i4.0
0x5ef0  stloc.s  8
0x5ef2  ldc.i4.0
0x5ef3  stloc.s  8
0x5ef5  br.s     loc_5F22
0x5ef7  ldloc.s  7
0x5ef9  ldloc.s  8
0x5efb  ldarg.0
0x5efc  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5f01  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_Actions_InsertionLocation()
0x5f06  ldarg.0
0x5f07  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_Actions_InsertionLocation_Offset
0x5f0c  ldelem.i4
0x5f0d  stelem.i4
0x5f0e  ldarg.0
0x5f0f  ldarg.0
0x5f10  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_Actions_InsertionLocation_Offset
0x5f15  ldc.i4.1
0x5f16  add
0x5f17  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_Actions_InsertionLocation_Offset
0x5f1c  ldloc.s  8
0x5f1e  ldc.i4.1
0x5f1f  add
0x5f20  stloc.s  8
0x5f22  ldloc.s  8
0x5f24  ldloc.s  6
0x5f26  blt.s    loc_5EF7
0x5f28  ldloca.s 0
0x5f2a  ldloc.s  7
0x5f2c  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::SetInsertionLocation(valuetype Microsoft.ManagementConsole.Internal.ActionsInsertionLocation[] value)
0x5f31  ldarg.0
0x5f32  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5f37  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_Actions_DisplayName_Count()
0x5f3c  ldarg.0
0x5f3d  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5f42  ldelem.i4
0x5f43  stloc.s  9
0x5f45  ldnull
0x5f46  stloc.s  0xA
0x5f48  ldloc.s  9
0x5f4a  ldc.i4.0
0x5f4b  blt.s    loc_5F56
0x5f4d  ldloc.s  9
0x5f4f  newarr   [mscorlib]System.String
0x5f54  stloc.s  0xA
0x5f56  ldc.i4.0
0x5f57  stloc.s  0xB
0x5f59  ldc.i4.0
0x5f5a  stloc.s  0xB
0x5f5c  br.s     loc_5F82
0x5f5e  ldloc.s  0xA
0x5f60  ldloc.s  0xB
0x5f62  ldarg.0
0x5f63  ldfld    class [mscorlib]System.IO.BinaryReader Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_strings
0x5f68  callvirt instance string [mscorlib]System.IO.BinaryReader::ReadString()
0x5f6d  stelem.ref
0x5f6e  ldarg.0
0x5f6f  ldarg.0
0x5f70  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_Actions_DisplayName_Offset
0x5f75  ldc.i4.1
0x5f76  add
0x5f77  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_Actions_DisplayName_Offset
0x5f7c  ldloc.s  0xB
0x5f7e  ldc.i4.1
0x5f7f  add
0x5f80  stloc.s  0xB
0x5f82  ldloc.s  0xB
0x5f84  ldloc.s  9
0x5f86  blt.s    loc_5F5E
0x5f88  ldloca.s 0
0x5f8a  ldloc.s  0xA
0x5f8c  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::SetDisplayName(string[] value)
0x5f91  ldarg.0
0x5f92  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5f97  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_Actions_MnemonicDisplayName_Count()
0x5f9c  ldarg.0
0x5f9d  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5fa2  ldelem.i4
0x5fa3  stloc.s  0xC
0x5fa5  ldnull
0x5fa6  stloc.s  0xD
0x5fa8  ldloc.s  0xC
0x5faa  ldc.i4.0
0x5fab  blt.s    loc_5FB6
0x5fad  ldloc.s  0xC
0x5faf  newarr   [mscorlib]System.String
0x5fb4  stloc.s  0xD
0x5fb6  ldc.i4.0
0x5fb7  stloc.s  0xE
0x5fb9  ldc.i4.0
0x5fba  stloc.s  0xE
0x5fbc  br.s     loc_5FE2
0x5fbe  ldloc.s  0xD
0x5fc0  ldloc.s  0xE
0x5fc2  ldarg.0
0x5fc3  ldfld    class [mscorlib]System.IO.BinaryReader Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_strings
0x5fc8  callvirt instance string [mscorlib]System.IO.BinaryReader::ReadString()
0x5fcd  stelem.ref
0x5fce  ldarg.0
0x5fcf  ldarg.0
0x5fd0  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_Actions_MnemonicDisplayName_Offset
0x5fd5  ldc.i4.1
0x5fd6  add
0x5fd7  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_Actions_MnemonicDisplayName_Offset
0x5fdc  ldloc.s  0xE
0x5fde  ldc.i4.1
0x5fdf  add
0x5fe0  stloc.s  0xE
0x5fe2  ldloc.s  0xE
0x5fe4  ldloc.s  0xC
0x5fe6  blt.s    loc_5FBE
0x5fe8  ldloca.s 0
0x5fea  ldloc.s  0xD
0x5fec  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::SetMnemonicDisplayName(string[] value)
0x5ff1  ldarg.0
0x5ff2  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5ff7  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_Actions_Description_Count()
0x5ffc  ldarg.0
0x5ffd  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x6002  ldelem.i4
0x6003  stloc.s  0xF
0x6005  ldnull
0x6006  stloc.s  0x10
0x6008  ldloc.s  0xF
0x600a  ldc.i4.0
0x600b  blt.s    loc_6016
0x600d  ldloc.s  0xF
0x600f  newarr   [mscorlib]System.String
0x6014  stloc.s  0x10
0x6016  ldc.i4.0
0x6017  stloc.s  0x11
0x6019  ldc.i4.0
0x601a  stloc.s  0x11
0x601c  br.s     loc_6042
0x601e  ldloc.s  0x10
0x6020  ldloc.s  0x11
0x6022  ldarg.0
0x6023  ldfld    class [mscorlib]System.IO.BinaryReader Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_strings
0x6028  callvirt instance string [mscorlib]System.IO.BinaryReader::ReadString()
0x602d  stelem.ref
0x602e  ldarg.0
0x602f  ldarg.0
0x6030  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_Actions_Description_Offset
0x6035  ldc.i4.1
0x6036  add
0x6037  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_Actions_Description_Offset
0x603c  ldloc.s  0x11
0x603e  ldc.i4.1
0x603f  add
0x6040  stloc.s  0x11
0x6042  ldloc.s  0x11
0x6044  ldloc.s  0xF
0x6046  blt.s    loc_601E
0x6048  ldloca.s 0
0x604a  ldloc.s  0x10
0x604c  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::SetDescription(string[] value)
0x6051  ldarg.0
0x6052  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x6057  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_Actions_LanguageIndependentName_Count()
0x605c  ldarg.0
0x605d  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x6062  ldelem.i4
0x6063  stloc.s  0x12
0x6065  ldnull
0x6066  stloc.s  0x13
0x6068  ldloc.s  0x12
0x606a  ldc.i4.0
0x606b  blt.s    loc_6076
0x606d  ldloc.s  0x12
0x606f  newarr   [mscorlib]System.String
0x6074  stloc.s  0x13
0x6076  ldc.i4.0
0x6077  stloc.s  0x14
0x6079  ldc.i4.0
0x607a  stloc.s  0x14
0x607c  br.s     loc_60A2
0x607e  ldloc.s  0x13
0x6080  ldloc.s  0x14
0x6082  ldarg.0
0x6083  ldfld    class [mscorlib]System.IO.BinaryReader Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_strings
0x6088  callvirt instance string [mscorlib]System.IO.BinaryReader::ReadString()
0x608d  stelem.ref
0x608e  ldarg.0
0x608f  ldarg.0
0x6090  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_Actions_LanguageIndependentName_Offset
0x6095  ldc.i4.1
0x6096  add
0x6097  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_Actions_LanguageIndependentName_Offset
0x609c  ldloc.s  0x14
0x609e  ldc.i4.1
0x609f  add
0x60a0  stloc.s  0x14
0x60a2  ldloc.s  0x14
0x60a4  ldloc.s  0x12
0x60a6  blt.s    loc_607E
0x60a8  ldloca.s 0
0x60aa  ldloc.s  0x13
0x60ac  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::SetLanguageIndependentName(string[] value)
0x60b1  ldarg.0
0x60b2  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x60b7  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_Actions_ImageIndex_Count()
0x60bc  ldarg.0
0x60bd  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x60c2  ldelem.i4
0x60c3  stloc.s  0x15
  ... truncated ...
```
