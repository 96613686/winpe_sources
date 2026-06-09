# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextInitialSharedData

- ea: `0x5ba0`
- end: `0x5d17`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextInitialSharedData`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x58d0`

## callees

- `0xd80`
- `0xda0`
- `0xdc0`
- `0xde0`
- `0x5ba0`
- `0x5d20`
- `0x5d60`
- `0x5da0`
- `0x7b80`
- `0x7bc0`
- `0x7c00`
- `0x7c60`

## pseudocode

```c

```

## disassembly

```asm
0x5ba0  ldarg.0
0x5ba1  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5ba6  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_InitialSharedData_AddedFormats_Count()
0x5bab  ldarg.0
0x5bac  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5bb1  ldelem.i4
0x5bb2  stloc.0
0x5bb3  ldnull
0x5bb4  stloc.1
0x5bb5  ldloc.0
0x5bb6  ldc.i4.0
0x5bb7  blt.s    loc_5BC0
0x5bb9  ldloc.0
0x5bba  newarr   Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0x5bbf  stloc.1
0x5bc0  ldc.i4.0
0x5bc1  stloc.2
0x5bc2  ldc.i4.0
0x5bc3  stloc.2
0x5bc4  br.s     loc_5BEA
0x5bc6  ldloc.1
0x5bc7  ldloc.2
0x5bc8  ldelema  Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0x5bcd  ldarg.0
0x5bce  call     instance valuetype Microsoft.ManagementConsole.Internal.DataFormatConfiguration Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextAddedFormats()
0x5bd3  stobj    Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0x5bd8  ldarg.0
0x5bd9  ldarg.0
0x5bda  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_InitialSharedData_AddedFormats_Offset
0x5bdf  ldc.i4.1
0x5be0  add
0x5be1  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_InitialSharedData_AddedFormats_Offset
0x5be6  ldloc.2
0x5be7  ldc.i4.1
0x5be8  add
0x5be9  stloc.2
0x5bea  ldloc.2
0x5beb  ldloc.0
0x5bec  blt.s    loc_5BC6
0x5bee  ldarg.1
0x5bef  ldloc.1
0x5bf0  callvirt instance void Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate::SetAddedFormats(valuetype Microsoft.ManagementConsole.Internal.DataFormatConfiguration[] addedFormats)
0x5bf5  ldarg.0
0x5bf6  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5bfb  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_InitialSharedData_ChangedFormats_Count()
0x5c00  ldarg.0
0x5c01  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5c06  ldelem.i4
0x5c07  stloc.3
0x5c08  ldnull
0x5c09  stloc.s  4
0x5c0b  ldloc.3
0x5c0c  ldc.i4.0
0x5c0d  blt.s    loc_5C17
0x5c0f  ldloc.3
0x5c10  newarr   Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0x5c15  stloc.s  4
0x5c17  ldc.i4.0
0x5c18  stloc.s  5
0x5c1a  ldc.i4.0
0x5c1b  stloc.s  5
0x5c1d  br.s     loc_5C47
0x5c1f  ldloc.s  4
0x5c21  ldloc.s  5
0x5c23  ldelema  Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0x5c28  ldarg.0
0x5c29  call     instance valuetype Microsoft.ManagementConsole.Internal.DataFormatConfiguration Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextChangedFormats()
0x5c2e  stobj    Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0x5c33  ldarg.0
0x5c34  ldarg.0
0x5c35  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_InitialSharedData_ChangedFormats_Offset
0x5c3a  ldc.i4.1
0x5c3b  add
0x5c3c  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_InitialSharedData_ChangedFormats_Offset
0x5c41  ldloc.s  5
0x5c43  ldc.i4.1
0x5c44  add
0x5c45  stloc.s  5
0x5c47  ldloc.s  5
0x5c49  ldloc.3
0x5c4a  blt.s    loc_5C1F
0x5c4c  ldarg.1
0x5c4d  ldloc.s  4
0x5c4f  callvirt instance void Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate::SetChangedFormats(valuetype Microsoft.ManagementConsole.Internal.DataFormatConfiguration[] changedFormats)
0x5c54  ldarg.0
0x5c55  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5c5a  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_InitialSharedData_UpdatedData_Count()
0x5c5f  ldarg.0
0x5c60  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5c65  ldelem.i4
0x5c66  stloc.s  6
0x5c68  ldnull
0x5c69  stloc.s  7
0x5c6b  ldloc.s  6
0x5c6d  ldc.i4.0
0x5c6e  blt.s    loc_5C79
0x5c70  ldloc.s  6
0x5c72  newarr   Microsoft.ManagementConsole.Internal.ClipboardData
0x5c77  stloc.s  7
0x5c79  ldc.i4.0
0x5c7a  stloc.s  8
0x5c7c  ldc.i4.0
0x5c7d  stloc.s  8
0x5c7f  br.s     loc_5CA9
0x5c81  ldloc.s  7
0x5c83  ldloc.s  8
0x5c85  ldelema  Microsoft.ManagementConsole.Internal.ClipboardData
0x5c8a  ldarg.0
0x5c8b  call     instance valuetype Microsoft.ManagementConsole.Internal.ClipboardData Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextUpdatedData()
0x5c90  stobj    Microsoft.ManagementConsole.Internal.ClipboardData
0x5c95  ldarg.0
0x5c96  ldarg.0
0x5c97  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_InitialSharedData_UpdatedData_Offset
0x5c9c  ldc.i4.1
0x5c9d  add
0x5c9e  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_InitialSharedData_UpdatedData_Offset
0x5ca3  ldloc.s  8
0x5ca5  ldc.i4.1
0x5ca6  add
0x5ca7  stloc.s  8
0x5ca9  ldloc.s  8
0x5cab  ldloc.s  6
0x5cad  blt.s    loc_5C81
0x5caf  ldarg.1
0x5cb0  ldloc.s  7
0x5cb2  callvirt instance void Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate::SetUpdatedData(valuetype Microsoft.ManagementConsole.Internal.ClipboardData[] updatedData)
0x5cb7  ldarg.0
0x5cb8  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5cbd  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_InitialSharedData_RemovedClipboardFormatIds_Count()
0x5cc2  ldarg.0
0x5cc3  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x5cc8  ldelem.i4
0x5cc9  stloc.s  9
0x5ccb  ldnull
0x5ccc  stloc.s  0xA
0x5cce  ldloc.s  9
0x5cd0  ldc.i4.0
0x5cd1  blt.s    loc_5CDC
0x5cd3  ldloc.s  9
0x5cd5  newarr   [mscorlib]System.String
0x5cda  stloc.s  0xA
0x5cdc  ldc.i4.0
0x5cdd  stloc.s  0xB
0x5cdf  ldc.i4.0
0x5ce0  stloc.s  0xB
0x5ce2  br.s     loc_5D08
0x5ce4  ldloc.s  0xA
0x5ce6  ldloc.s  0xB
0x5ce8  ldarg.0
0x5ce9  ldfld    class [mscorlib]System.IO.BinaryReader Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_strings
0x5cee  callvirt instance string [mscorlib]System.IO.BinaryReader::ReadString()
0x5cf3  stelem.ref
0x5cf4  ldarg.0
0x5cf5  ldarg.0
0x5cf6  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_InitialSharedData_RemovedClipboardFormatIds_Offset
0x5cfb  ldc.i4.1
0x5cfc  add
0x5cfd  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_InitialSharedData_RemovedClipboardFormatIds_Offset
0x5d02  ldloc.s  0xB
0x5d04  ldc.i4.1
0x5d05  add
0x5d06  stloc.s  0xB
0x5d08  ldloc.s  0xB
0x5d0a  ldloc.s  9
0x5d0c  blt.s    loc_5CE4
0x5d0e  ldarg.1
0x5d0f  ldloc.s  0xA
0x5d11  callvirt instance void Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate::SetRemovedClipboardFormatIds(string[] removedClipboardFormatIds)
0x5d16  ret
```
