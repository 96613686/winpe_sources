# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::.ctor

- ea: `0x6740`
- end: `0x6a59`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::.ctor`
- size: `793`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x7970`
- `0x8180`
- `0x8290`
- `0x83b0`
- `0x84d0`
- `0x85f0`

## pseudocode

```c

```

## disassembly

```asm
0x6740  ldarg.0
0x6741  newobj   instance void Microsoft.ManagementConsole.Internal.GuidList::.ctor()
0x6746  stfld    class Microsoft.ManagementConsole.Internal.GuidList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_NodeType
0x674b  ldarg.0
0x674c  newobj   instance void Microsoft.ManagementConsole.Internal.BooleanList::.ctor()
0x6751  stfld    class Microsoft.ManagementConsole.Internal.BooleanList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_AddedFormats_RequiresQuery
0x6756  ldarg.0
0x6757  newobj   instance void Microsoft.ManagementConsole.Internal.BooleanList::.ctor()
0x675c  stfld    class Microsoft.ManagementConsole.Internal.BooleanList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_ChangedFormats_RequiresQuery
0x6761  ldarg.0
0x6762  newobj   instance void Microsoft.ManagementConsole.Internal.ByteList::.ctor()
0x6767  stfld    class Microsoft.ManagementConsole.Internal.ByteList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_UpdatedData_Value
0x676c  ldarg.0
0x676d  newobj   instance void Microsoft.ManagementConsole.Internal.Int32List::.ctor()
0x6772  stfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_UpdatedData_Value_Count
0x6777  ldarg.0
0x6778  newobj   instance void Microsoft.ManagementConsole.Internal.Int32List::.ctor()
0x677d  stfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_Id
0x6782  ldarg.0
0x6783  newobj   instance void Microsoft.ManagementConsole.Internal.Int32List::.ctor()
0x6788  stfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ItemType
0x678d  ldarg.0
0x678e  newobj   instance void Microsoft.ManagementConsole.Internal.Int32List::.ctor()
0x6793  stfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_InsertionLocation
0x6798  ldarg.0
0x6799  newobj   instance void Microsoft.ManagementConsole.Internal.Int32List::.ctor()
0x679e  stfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ImageIndex
0x67a3  ldarg.0
0x67a4  newobj   instance void Microsoft.ManagementConsole.Internal.Int32List::.ctor()
0x67a9  stfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_State
0x67ae  ldarg.0
0x67af  newobj   instance void Microsoft.ManagementConsole.Internal.BooleanList::.ctor()
0x67b4  stfld    class Microsoft.ManagementConsole.Internal.BooleanList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ExecuteSync
0x67b9  ldarg.0
0x67ba  newobj   instance void Microsoft.ManagementConsole.Internal.BooleanList::.ctor()
0x67bf  stfld    class Microsoft.ManagementConsole.Internal.BooleanList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_RenderAsRegion
0x67c4  ldarg.0
0x67c5  newobj   instance void Microsoft.ManagementConsole.Internal.Int32List::.ctor()
0x67ca  stfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ItemsCount
0x67cf  ldarg.0
0x67d0  newobj   instance void Microsoft.ManagementConsole.Internal.Int32List::.ctor()
0x67d5  stfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_Id
0x67da  ldarg.0
0x67db  newobj   instance void Microsoft.ManagementConsole.Internal.Int32List::.ctor()
0x67e0  stfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_ItemType
0x67e5  ldarg.0
0x67e6  newobj   instance void Microsoft.ManagementConsole.Internal.Int32List::.ctor()
0x67eb  stfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_InsertionLocation
0x67f0  ldarg.0
0x67f1  newobj   instance void Microsoft.ManagementConsole.Internal.Int32List::.ctor()
0x67f6  stfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_ImageIndex
0x67fb  ldarg.0
0x67fc  newobj   instance void Microsoft.ManagementConsole.Internal.Int32List::.ctor()
0x6801  stfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_State
0x6806  ldarg.0
0x6807  newobj   instance void Microsoft.ManagementConsole.Internal.BooleanList::.ctor()
0x680c  stfld    class Microsoft.ManagementConsole.Internal.BooleanList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_ExecuteSync
0x6811  ldarg.0
0x6812  newobj   instance void Microsoft.ManagementConsole.Internal.BooleanList::.ctor()
0x6817  stfld    class Microsoft.ManagementConsole.Internal.BooleanList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_RenderAsRegion
0x681c  ldarg.0
0x681d  newobj   instance void Microsoft.ManagementConsole.Internal.Int32List::.ctor()
0x6822  stfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_ItemsCount
0x6827  ldarg.0
0x6828  call     instance void [mscorlib]System.Object::.ctor()
0x682d  ldarg.0
0x682e  newobj   instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::.ctor()
0x6833  stfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x6838  ldarg.0
0x6839  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_target
0x683e  ldarg.1
0x683f  callvirt instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::set_Count(int32 value)
0x6844  ldarg.0
0x6845  ldarg.1
0x6846  newarr   [mscorlib]System.Int32
0x684b  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_ParentScopeNodeId
0x6850  ldarg.0
0x6851  ldarg.1
0x6852  newarr   [mscorlib]System.Int32
0x6857  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InsertionIndex
0x685c  ldarg.0
0x685d  ldarg.1
0x685e  newarr   [mscorlib]System.Int32
0x6863  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_NodeType_Id
0x6868  ldarg.0
0x6869  ldarg.1
0x686a  newarr   [mscorlib]System.Int32
0x686f  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_SelectedImageIndex
0x6874  ldarg.0
0x6875  ldarg.1
0x6876  newarr   [mscorlib]System.Boolean
0x687b  stfld    bool[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_HideExpandIcon
0x6880  ldarg.0
0x6881  ldarg.1
0x6882  newarr   [mscorlib]System.Boolean
0x6887  stfld    bool[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_SendActivation
0x688c  ldarg.0
0x688d  ldarg.1
0x688e  newarr   [mscorlib]System.Boolean
0x6893  stfld    bool[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_SendDeactivation
0x6898  ldarg.0
0x6899  ldarg.1
0x689a  newarr   [mscorlib]System.Int32
0x689f  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_ViewSetId
0x68a4  ldarg.0
0x68a5  ldarg.1
0x68a6  newarr   [mscorlib]System.Int32
0x68ab  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_EnabledVerbs
0x68b0  ldarg.0
0x68b1  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x68b6  stfld    class [mscorlib]System.IO.MemoryStream Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_stream_strings
0x68bb  ldarg.0
0x68bc  ldarg.0
0x68bd  ldfld    class [mscorlib]System.IO.MemoryStream Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_stream_strings
0x68c2  newobj   instance void [mscorlib]System.IO.BinaryWriter::.ctor(class [mscorlib]System.IO.Stream)
0x68c7  stfld    class [mscorlib]System.IO.BinaryWriter Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_strings
0x68cc  ldarg.0
0x68cd  ldarg.1
0x68ce  newarr   [mscorlib]System.Int32
0x68d3  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_PasteTargetInfo_DefaultDragAndDropVerb
0x68d8  ldarg.0
0x68d9  ldarg.1
0x68da  newarr   [mscorlib]System.Int32
0x68df  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_PasteTargetInfo_AllowedClipboardFormats_Count
0x68e4  ldarg.0
0x68e5  ldarg.1
0x68e6  newarr   [mscorlib]System.Int32
0x68eb  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_Id
0x68f0  ldarg.0
0x68f1  ldarg.1
0x68f2  newarr   [mscorlib]System.Int32
0x68f7  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_ImageIndex
0x68fc  ldarg.0
0x68fd  ldarg.1
0x68fe  newarr   [mscorlib]System.Int32
0x6903  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_NodeData_SubItems_Count
0x6908  ldarg.0
0x6909  ldarg.1
0x690a  newarr   [mscorlib]System.Int32
0x690f  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_AddedFormats_Count
0x6914  ldarg.0
0x6915  ldarg.1
0x6916  newarr   [mscorlib]System.Int32
0x691b  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_ChangedFormats_Count
0x6920  ldarg.0
0x6921  ldarg.1
0x6922  newarr   [mscorlib]System.Int32
0x6927  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_UpdatedData_Count
0x692c  ldarg.0
0x692d  ldarg.1
0x692e  newarr   [mscorlib]System.Int32
0x6933  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_RemovedClipboardFormatIds_Count
0x6938  ldarg.0
0x6939  ldarg.1
0x693a  newarr   [mscorlib]System.Int32
0x693f  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_Id_Count
0x6944  ldarg.0
0x6945  ldarg.1
0x6946  newarr   [mscorlib]System.Int32
0x694b  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ItemType_Count
0x6950  ldarg.0
0x6951  ldarg.1
0x6952  newarr   [mscorlib]System.Int32
0x6957  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_InsertionLocation_Count
0x695c  ldarg.0
0x695d  ldarg.1
0x695e  newarr   [mscorlib]System.Int32
0x6963  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_DisplayName_Count
0x6968  ldarg.0
0x6969  ldarg.1
0x696a  newarr   [mscorlib]System.Int32
0x696f  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_MnemonicDisplayName_Count
0x6974  ldarg.0
0x6975  ldarg.1
0x6976  newarr   [mscorlib]System.Int32
0x697b  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_Description_Count
0x6980  ldarg.0
0x6981  ldarg.1
0x6982  newarr   [mscorlib]System.Int32
0x6987  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_LanguageIndependentName_Count
0x698c  ldarg.0
0x698d  ldarg.1
0x698e  newarr   [mscorlib]System.Int32
0x6993  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ImageIndex_Count
0x6998  ldarg.0
0x6999  ldarg.1
0x699a  newarr   [mscorlib]System.Int32
0x699f  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_State_Count
0x69a4  ldarg.0
0x69a5  ldarg.1
0x69a6  newarr   [mscorlib]System.Int32
0x69ab  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ExecuteSync_Count
0x69b0  ldarg.0
0x69b1  ldarg.1
0x69b2  newarr   [mscorlib]System.Int32
0x69b7  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_RenderAsRegion_Count
0x69bc  ldarg.0
0x69bd  ldarg.1
0x69be  newarr   [mscorlib]System.Int32
0x69c3  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ItemsCount_Count
0x69c8  ldarg.0
0x69c9  ldarg.1
0x69ca  newarr   [mscorlib]System.Int32
0x69cf  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_Id_Count
0x69d4  ldarg.0
0x69d5  ldarg.1
0x69d6  newarr   [mscorlib]System.Int32
0x69db  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_ItemType_Count
0x69e0  ldarg.0
0x69e1  ldarg.1
0x69e2  newarr   [mscorlib]System.Int32
0x69e7  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_InsertionLocation_Count
0x69ec  ldarg.0
0x69ed  ldarg.1
0x69ee  newarr   [mscorlib]System.Int32
0x69f3  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_DisplayName_Count
0x69f8  ldarg.0
0x69f9  ldarg.1
0x69fa  newarr   [mscorlib]System.Int32
0x69ff  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_MnemonicDisplayName_Count
0x6a04  ldarg.0
0x6a05  ldarg.1
0x6a06  newarr   [mscorlib]System.Int32
0x6a0b  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_Description_Count
0x6a10  ldarg.0
0x6a11  ldarg.1
0x6a12  newarr   [mscorlib]System.Int32
0x6a17  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_LanguageIndependentName_Count
0x6a1c  ldarg.0
0x6a1d  ldarg.1
0x6a1e  newarr   [mscorlib]System.Int32
0x6a23  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_ImageIndex_Count
0x6a28  ldarg.0
0x6a29  ldarg.1
0x6a2a  newarr   [mscorlib]System.Int32
0x6a2f  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_State_Count
0x6a34  ldarg.0
0x6a35  ldarg.1
0x6a36  newarr   [mscorlib]System.Int32
0x6a3b  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_ExecuteSync_Count
0x6a40  ldarg.0
0x6a41  ldarg.1
0x6a42  newarr   [mscorlib]System.Int32
0x6a47  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_RenderAsRegion_Count
0x6a4c  ldarg.0
0x6a4d  ldarg.1
0x6a4e  newarr   [mscorlib]System.Int32
0x6a53  stfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_ItemsCount_Count
0x6a58  ret
```
