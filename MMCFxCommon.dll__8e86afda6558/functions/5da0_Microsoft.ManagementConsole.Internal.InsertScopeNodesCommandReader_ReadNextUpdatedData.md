# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextUpdatedData

- ea: `0x5da0`
- end: `0x5e0b`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextUpdatedData`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5ba0`

## callees

- `0xc20`
- `0xc40`
- `0x5da0`
- `0x7c20`
- `0x7c40`

## pseudocode

```c

```

## disassembly

```asm
0x5da0  ldloca.s 0
0x5da2  initobj  Microsoft.ManagementConsole.Internal.ClipboardData
0x5da8  ldloca.s 0
0x5daa  ldarg.0
0x5dab  ldfld    class [mscorlib]System.IO.BinaryReader Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_strings
0x5db0  callvirt instance string [mscorlib]System.IO.BinaryReader::ReadString()
0x5db5  call     instance void Microsoft.ManagementConsole.Internal.ClipboardData::set_ClipboardFormatId(string value)
0x5dba  ldarg.0
0x5dbb  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5dc0  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_InitialSharedData_UpdatedData_Value_Count()
0x5dc5  ldarg.0
0x5dc6  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_InitialSharedData_UpdatedData_Offset
0x5dcb  ldelem.i4
0x5dcc  stloc.1
0x5dcd  ldnull
0x5dce  stloc.2
0x5dcf  ldloc.1
0x5dd0  ldc.i4.0
0x5dd1  blt.s    loc_5E01
0x5dd3  ldloc.1
0x5dd4  newarr   [mscorlib]System.Byte
0x5dd9  stloc.2
0x5dda  ldarg.0
0x5ddb  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x5de0  callvirt instance unsigned int8[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_InitialSharedData_UpdatedData_Value()
0x5de5  ldarg.0
0x5de6  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_InitialSharedData_UpdatedData_Value_Offset
0x5deb  ldloc.2
0x5dec  ldc.i4.0
0x5ded  ldloc.1
0x5dee  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x5df3  ldarg.0
0x5df4  ldarg.0
0x5df5  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_InitialSharedData_UpdatedData_Value_Offset
0x5dfa  ldloc.1
0x5dfb  add
0x5dfc  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_InitialSharedData_UpdatedData_Value_Offset
0x5e01  ldloca.s 0
0x5e03  ldloc.2
0x5e04  call     instance void Microsoft.ManagementConsole.Internal.ClipboardData::SetValue(unsigned int8[] value)
0x5e09  ldloc.0
0x5e0a  ret
```
