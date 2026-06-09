# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::Flush

- ea: `0x6a60`
- end: `0x6f15`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::Flush`
- size: `1205`
- prototype: ``
- caller_count: `0`
- callee_count: `68`
- tags: `broker_com_uri`

## callees

- `0x7990`
- `0x79b0`
- `0x79d0`
- `0x79f0`
- `0x7a10`
- `0x7a30`
- `0x7a50`
- `0x7a70`
- `0x7a90`
- `0x7ab0`
- `0x7ad0`
- `0x7af0`
- `0x7b10`
- `0x7b30`
- `0x7b50`
- `0x7b70`
- `0x7b90`
- `0x7bb0`
- `0x7bd0`
- `0x7bf0`
- `0x7c10`
- `0x7c30`
- `0x7c50`
- `0x7c70`
- `0x7c90`
- `0x7cb0`
- `0x7cd0`
- `0x7cf0`
- `0x7d10`
- `0x7d30`
- `0x7d50`
- `0x7d70`
- `0x7d90`
- `0x7db0`
- `0x7dd0`
- `0x7df0`
- `0x7e10`
- `0x7e30`
- `0x7e50`
- `0x7e70`
- `0x7e90`
- `0x7eb0`
- `0x7ed0`
- `0x7ef0`
- `0x7f10`
- `0x7f30`
- `0x7f50`
- `0x7f70`
- `0x7f90`
- `0x7fb0`

## pseudocode

```c

```

## disassembly

```asm
0x6a60  ldarg.0
0x6a61  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6a66  ldarg.0
0x6a67  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_ParentScopeNodeId
0x6a6c  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_ParentScopeNodeId(int32[] ParentScopeNodeId)
0x6a71  ldarg.0
0x6a72  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6a77  ldarg.0
0x6a78  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InsertionIndex
0x6a7d  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_InsertionIndex(int32[] InsertionIndex)
0x6a82  ldarg.0
0x6a83  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6a88  ldarg.0
0x6a89  ldfld    class Microsoft.ManagementConsole.Internal.GuidList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_NodeType
0x6a8e  callvirt instance valuetype [mscorlib]System.Guid[] Microsoft.ManagementConsole.Internal.GuidList::ToArray()
0x6a93  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_NodeData_NodeType(valuetype [mscorlib]System.Guid[] NodeType)
0x6a98  ldarg.0
0x6a99  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6a9e  ldarg.0
0x6a9f  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_NodeType_Id
0x6aa4  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_NodeData_NodeType_Id(int32[] NodeType_Id)
0x6aa9  ldarg.0
0x6aaa  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6aaf  ldarg.0
0x6ab0  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_SelectedImageIndex
0x6ab5  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_NodeData_SelectedImageIndex(int32[] SelectedImageIndex)
0x6aba  ldarg.0
0x6abb  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6ac0  ldarg.0
0x6ac1  ldfld    bool[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_HideExpandIcon
0x6ac6  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_NodeData_HideExpandIcon(bool[] HideExpandIcon)
0x6acb  ldarg.0
0x6acc  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6ad1  ldarg.0
0x6ad2  ldfld    bool[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_SendActivation
0x6ad7  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_NodeData_SendActivation(bool[] SendActivation)
0x6adc  ldarg.0
0x6add  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6ae2  ldarg.0
0x6ae3  ldfld    bool[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_SendDeactivation
0x6ae8  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_NodeData_SendDeactivation(bool[] SendDeactivation)
0x6aed  ldarg.0
0x6aee  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6af3  ldarg.0
0x6af4  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_ViewSetId
0x6af9  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_NodeData_ViewSetId(int32[] ViewSetId)
0x6afe  ldarg.0
0x6aff  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6b04  ldarg.0
0x6b05  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_EnabledVerbs
0x6b0a  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_NodeData_EnabledVerbs(int32[] EnabledVerbs)
0x6b0f  ldarg.0
0x6b10  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6b15  ldarg.0
0x6b16  ldfld    class [mscorlib]System.IO.MemoryStream Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_stream_strings
0x6b1b  callvirt instance unsigned int8[] [mscorlib]System.IO.MemoryStream::GetBuffer()
0x6b20  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_strings(unsigned int8[] strings)
0x6b25  ldarg.0
0x6b26  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6b2b  ldarg.0
0x6b2c  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_PasteTargetInfo_DefaultDragAndDropVerb
0x6b31  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_NodeData_PasteTargetInfo_DefaultDragAndDropVerb(int32[] DefaultDragAndDropVerb)
0x6b36  ldarg.0
0x6b37  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6b3c  ldarg.0
0x6b3d  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_PasteTargetInfo_AllowedClipboardFormats_Count
0x6b42  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_NodeData_PasteTargetInfo_AllowedClipboardFormats_Count(int32[] AllowedClipboardFormats_Count)
0x6b47  ldarg.0
0x6b48  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6b4d  ldarg.0
0x6b4e  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_Id
0x6b53  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_NodeData_Id(int32[] Id)
0x6b58  ldarg.0
0x6b59  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6b5e  ldarg.0
0x6b5f  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_ImageIndex
0x6b64  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_NodeData_ImageIndex(int32[] ImageIndex)
0x6b69  ldarg.0
0x6b6a  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6b6f  ldarg.0
0x6b70  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_SubItems_Count
0x6b75  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_NodeData_SubItems_Count(int32[] SubItems_Count)
0x6b7a  ldarg.0
0x6b7b  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6b80  ldarg.0
0x6b81  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_AddedFormats_Count
0x6b86  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_InitialSharedData_AddedFormats_Count(int32[] AddedFormats_Count)
0x6b8b  ldarg.0
0x6b8c  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6b91  ldarg.0
0x6b92  ldfld    class Microsoft.ManagementConsole.Internal.BooleanList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_AddedFormats_RequiresQuery
0x6b97  callvirt instance bool[] Microsoft.ManagementConsole.Internal.BooleanList::ToArray()
0x6b9c  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_InitialSharedData_AddedFormats_RequiresQuery(bool[] RequiresQuery)
0x6ba1  ldarg.0
0x6ba2  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6ba7  ldarg.0
0x6ba8  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_ChangedFormats_Count
0x6bad  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_InitialSharedData_ChangedFormats_Count(int32[] ChangedFormats_Count)
0x6bb2  ldarg.0
0x6bb3  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6bb8  ldarg.0
0x6bb9  ldfld    class Microsoft.ManagementConsole.Internal.BooleanList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_ChangedFormats_RequiresQuery
0x6bbe  callvirt instance bool[] Microsoft.ManagementConsole.Internal.BooleanList::ToArray()
0x6bc3  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_InitialSharedData_ChangedFormats_RequiresQuery(bool[] RequiresQuery)
0x6bc8  ldarg.0
0x6bc9  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6bce  ldarg.0
0x6bcf  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_UpdatedData_Count
0x6bd4  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_InitialSharedData_UpdatedData_Count(int32[] UpdatedData_Count)
0x6bd9  ldarg.0
0x6bda  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6bdf  ldarg.0
0x6be0  ldfld    class Microsoft.ManagementConsole.Internal.ByteList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_UpdatedData_Value
0x6be5  callvirt instance unsigned int8[] Microsoft.ManagementConsole.Internal.ByteList::ToArray()
0x6bea  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_InitialSharedData_UpdatedData_Value(unsigned int8[] Value)
0x6bef  ldarg.0
0x6bf0  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6bf5  ldarg.0
0x6bf6  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_UpdatedData_Value_Count
0x6bfb  callvirt instance int32[] Microsoft.ManagementConsole.Internal.Int32List::ToArray()
0x6c00  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_InitialSharedData_UpdatedData_Value_Count(int32[] Value_Count)
0x6c05  ldarg.0
0x6c06  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6c0b  ldarg.0
0x6c0c  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_RemovedClipboardFormatIds_Count
0x6c11  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_InitialSharedData_RemovedClipboardFormatIds_Count(int32[] RemovedClipboardFormatIds_Count)
0x6c16  ldarg.0
0x6c17  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6c1c  ldarg.0
0x6c1d  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_Id
0x6c22  callvirt instance int32[] Microsoft.ManagementConsole.Internal.Int32List::ToArray()
0x6c27  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_Id(int32[] Id)
0x6c2c  ldarg.0
0x6c2d  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6c32  ldarg.0
0x6c33  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_Id_Count
0x6c38  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_Id_Count(int32[] Id_Count)
0x6c3d  ldarg.0
0x6c3e  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6c43  ldarg.0
0x6c44  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ItemType_Count
0x6c49  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_ItemType_Count(int32[] ItemType_Count)
0x6c4e  ldarg.0
0x6c4f  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6c54  ldarg.0
0x6c55  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ItemType
0x6c5a  callvirt instance int32[] Microsoft.ManagementConsole.Internal.Int32List::ToArray()
0x6c5f  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_ItemType(int32[] ItemType)
0x6c64  ldarg.0
0x6c65  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6c6a  ldarg.0
0x6c6b  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_InsertionLocation_Count
0x6c70  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_InsertionLocation_Count(int32[] InsertionLocation_Count)
0x6c75  ldarg.0
0x6c76  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6c7b  ldarg.0
0x6c7c  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_InsertionLocation
0x6c81  callvirt instance int32[] Microsoft.ManagementConsole.Internal.Int32List::ToArray()
0x6c86  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_InsertionLocation(int32[] InsertionLocation)
0x6c8b  ldarg.0
0x6c8c  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6c91  ldarg.0
0x6c92  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_DisplayName_Count
0x6c97  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_DisplayName_Count(int32[] DisplayName_Count)
0x6c9c  ldarg.0
0x6c9d  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6ca2  ldarg.0
0x6ca3  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_MnemonicDisplayName_Count
0x6ca8  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_MnemonicDisplayName_Count(int32[] MnemonicDisplayName_Count)
0x6cad  ldarg.0
0x6cae  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6cb3  ldarg.0
0x6cb4  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_Description_Count
0x6cb9  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_Description_Count(int32[] Description_Count)
0x6cbe  ldarg.0
0x6cbf  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6cc4  ldarg.0
0x6cc5  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_LanguageIndependentName_Count
0x6cca  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_LanguageIndependentName_Count(int32[] LanguageIndependentName_Count)
0x6ccf  ldarg.0
0x6cd0  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6cd5  ldarg.0
0x6cd6  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ImageIndex
0x6cdb  callvirt instance int32[] Microsoft.ManagementConsole.Internal.Int32List::ToArray()
0x6ce0  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_ImageIndex(int32[] ImageIndex)
0x6ce5  ldarg.0
0x6ce6  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6ceb  ldarg.0
0x6cec  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ImageIndex_Count
0x6cf1  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_ImageIndex_Count(int32[] ImageIndex_Count)
0x6cf6  ldarg.0
0x6cf7  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6cfc  ldarg.0
0x6cfd  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_State_Count
0x6d02  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_State_Count(int32[] State_Count)
0x6d07  ldarg.0
0x6d08  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6d0d  ldarg.0
0x6d0e  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_State
0x6d13  callvirt instance int32[] Microsoft.ManagementConsole.Internal.Int32List::ToArray()
0x6d18  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_State(int32[] State)
0x6d1d  ldarg.0
0x6d1e  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6d23  ldarg.0
0x6d24  ldfld    class Microsoft.ManagementConsole.Internal.BooleanList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ExecuteSync
0x6d29  callvirt instance bool[] Microsoft.ManagementConsole.Internal.BooleanList::ToArray()
0x6d2e  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_ExecuteSync(bool[] ExecuteSync)
0x6d33  ldarg.0
0x6d34  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6d39  ldarg.0
0x6d3a  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ExecuteSync_Count
0x6d3f  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_ExecuteSync_Count(int32[] ExecuteSync_Count)
0x6d44  ldarg.0
0x6d45  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6d4a  ldarg.0
0x6d4b  ldfld    class Microsoft.ManagementConsole.Internal.BooleanList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_RenderAsRegion
0x6d50  callvirt instance bool[] Microsoft.ManagementConsole.Internal.BooleanList::ToArray()
0x6d55  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_RenderAsRegion(bool[] RenderAsRegion)
0x6d5a  ldarg.0
0x6d5b  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6d60  ldarg.0
0x6d61  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_RenderAsRegion_Count
0x6d66  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_RenderAsRegion_Count(int32[] RenderAsRegion_Count)
0x6d6b  ldarg.0
0x6d6c  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6d71  ldarg.0
0x6d72  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ItemsCount
0x6d77  callvirt instance int32[] Microsoft.ManagementConsole.Internal.Int32List::ToArray()
0x6d7c  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_ItemsCount(int32[] ItemsCount)
0x6d81  ldarg.0
0x6d82  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6d87  ldarg.0
0x6d88  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ItemsCount_Count
0x6d8d  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_Actions_ItemsCount_Count(int32[] ItemsCount_Count)
0x6d92  ldarg.0
0x6d93  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6d98  ldarg.0
0x6d99  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_Id
0x6d9e  callvirt instance int32[] Microsoft.ManagementConsole.Internal.Int32List::ToArray()
0x6da3  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_HelpActions_Id(int32[] Id)
0x6da8  ldarg.0
0x6da9  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6dae  ldarg.0
0x6daf  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_Id_Count
0x6db4  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_HelpActions_Id_Count(int32[] Id_Count)
0x6db9  ldarg.0
0x6dba  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6dbf  ldarg.0
0x6dc0  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_ItemType_Count
0x6dc5  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_HelpActions_ItemType_Count(int32[] ItemType_Count)
0x6dca  ldarg.0
0x6dcb  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6dd0  ldarg.0
0x6dd1  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_ItemType
0x6dd6  callvirt instance int32[] Microsoft.ManagementConsole.Internal.Int32List::ToArray()
0x6ddb  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_HelpActions_ItemType(int32[] ItemType)
0x6de0  ldarg.0
0x6de1  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6de6  ldarg.0
0x6de7  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_InsertionLocation_Count
0x6dec  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_HelpActions_InsertionLocation_Count(int32[] InsertionLocation_Count)
0x6df1  ldarg.0
0x6df2  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6df7  ldarg.0
0x6df8  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_InsertionLocation
0x6dfd  callvirt instance int32[] Microsoft.ManagementConsole.Internal.Int32List::ToArray()
0x6e02  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_HelpActions_InsertionLocation(int32[] InsertionLocation)
0x6e07  ldarg.0
0x6e08  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6e0d  ldarg.0
0x6e0e  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_DisplayName_Count
0x6e13  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_HelpActions_DisplayName_Count(int32[] DisplayName_Count)
0x6e18  ldarg.0
0x6e19  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6e1e  ldarg.0
0x6e1f  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_MnemonicDisplayName_Count
0x6e24  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_HelpActions_MnemonicDisplayName_Count(int32[] MnemonicDisplayName_Count)
0x6e29  ldarg.0
0x6e2a  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6e2f  ldarg.0
0x6e30  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_Description_Count
0x6e35  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_HelpActions_Description_Count(int32[] Description_Count)
0x6e3a  ldarg.0
0x6e3b  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6e40  ldarg.0
0x6e41  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_LanguageIndependentName_Count
0x6e46  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_HelpActions_LanguageIndependentName_Count(int32[] LanguageIndependentName_Count)
0x6e4b  ldarg.0
0x6e4c  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6e51  ldarg.0
0x6e52  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_ImageIndex
0x6e57  callvirt instance int32[] Microsoft.ManagementConsole.Internal.Int32List::ToArray()
0x6e5c  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_HelpActions_ImageIndex(int32[] ImageIndex)
0x6e61  ldarg.0
0x6e62  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6e67  ldarg.0
0x6e68  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_ImageIndex_Count
0x6e6d  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Set_HelpActions_ImageIndex_Count(int32[] ImageIndex_Count)
0x6e72  ldarg.0
0x6e73  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
  ... truncated ...
```
