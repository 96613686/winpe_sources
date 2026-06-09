# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextActions

- ea: `0x7350`
- end: `0x7627`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextActions`
- size: `727`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x6f20`

## callees

- `0x3f50`
- `0x3f70`
- `0x3f90`
- `0x3fb0`
- `0x3fd0`
- `0x3ff0`
- `0x4010`
- `0x4030`
- `0x4050`
- `0x4070`
- `0x4090`
- `0x40b0`
- `0x7130`
- `0x7350`
- `0x8320`
- `0x8530`
- `0x8560`

## pseudocode

```c

```

## disassembly

```asm
0x7350  ldarga.s 1
0x7352  call     instance int32[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetId()
0x7357  stloc.0
0x7358  ldc.i4.m1
0x7359  stloc.1
0x735a  ldloc.0
0x735b  brfalse.s loc_736D
0x735d  ldarg.0
0x735e  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_Id
0x7363  ldloc.0
0x7364  callvirt instance void Microsoft.ManagementConsole.Internal.Int32List::AddRange(int32[] items)
0x7369  ldloc.0
0x736a  ldlen
0x736b  conv.i4
0x736c  stloc.1
0x736d  ldarg.0
0x736e  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_Id_Count
0x7373  ldarg.0
0x7374  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x7379  ldloc.1
0x737a  stelem.i4
0x737b  ldarga.s 1
0x737d  call     instance valuetype Microsoft.ManagementConsole.Internal.ActionsPaneRootItemType[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetItemType()
0x7382  stloc.2
0x7383  ldc.i4.m1
0x7384  stloc.3
0x7385  ldloc.2
0x7386  brfalse.s loc_73AE
0x7388  ldloc.2
0x7389  ldlen
0x738a  conv.i4
0x738b  stloc.3
0x738c  ldc.i4.0
0x738d  stloc.s  4
0x738f  ldc.i4.0
0x7390  stloc.s  4
0x7392  br.s     loc_73A9
0x7394  ldarg.0
0x7395  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ItemType
0x739a  ldloc.2
0x739b  ldloc.s  4
0x739d  ldelem.i4
0x739e  callvirt instance void Microsoft.ManagementConsole.Internal.Int32List::Add(int32 item)
0x73a3  ldloc.s  4
0x73a5  ldc.i4.1
0x73a6  add
0x73a7  stloc.s  4
0x73a9  ldloc.s  4
0x73ab  ldloc.3
0x73ac  blt.s    loc_7394
0x73ae  ldarg.0
0x73af  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ItemType_Count
0x73b4  ldarg.0
0x73b5  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x73ba  ldloc.3
0x73bb  stelem.i4
0x73bc  ldarga.s 1
0x73be  call     instance valuetype Microsoft.ManagementConsole.Internal.ActionsInsertionLocation[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetInsertionLocation()
0x73c3  stloc.s  5
0x73c5  ldc.i4.m1
0x73c6  stloc.s  6
0x73c8  ldloc.s  5
0x73ca  brfalse.s loc_73F6
0x73cc  ldloc.s  5
0x73ce  ldlen
0x73cf  conv.i4
0x73d0  stloc.s  6
0x73d2  ldc.i4.0
0x73d3  stloc.s  7
0x73d5  ldc.i4.0
0x73d6  stloc.s  7
0x73d8  br.s     loc_73F0
0x73da  ldarg.0
0x73db  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_InsertionLocation
0x73e0  ldloc.s  5
0x73e2  ldloc.s  7
0x73e4  ldelem.i4
0x73e5  callvirt instance void Microsoft.ManagementConsole.Internal.Int32List::Add(int32 item)
0x73ea  ldloc.s  7
0x73ec  ldc.i4.1
0x73ed  add
0x73ee  stloc.s  7
0x73f0  ldloc.s  7
0x73f2  ldloc.s  6
0x73f4  blt.s    loc_73DA
0x73f6  ldarg.0
0x73f7  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_InsertionLocation_Count
0x73fc  ldarg.0
0x73fd  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x7402  ldloc.s  6
0x7404  stelem.i4
0x7405  ldarga.s 1
0x7407  call     instance string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetDisplayName()
0x740c  stloc.s  8
0x740e  ldc.i4.m1
0x740f  stloc.s  9
0x7411  ldloc.s  8
0x7413  brfalse.s loc_743A
0x7415  ldloc.s  8
0x7417  ldlen
0x7418  conv.i4
0x7419  stloc.s  9
0x741b  ldc.i4.0
0x741c  stloc.s  0xA
0x741e  ldc.i4.0
0x741f  stloc.s  0xA
0x7421  br.s     loc_7434
0x7423  ldarg.0
0x7424  ldloc.s  8
0x7426  ldloc.s  0xA
0x7428  ldelem.ref
0x7429  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteString(string value)
0x742e  ldloc.s  0xA
0x7430  ldc.i4.1
0x7431  add
0x7432  stloc.s  0xA
0x7434  ldloc.s  0xA
0x7436  ldloc.s  9
0x7438  blt.s    loc_7423
0x743a  ldarg.0
0x743b  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_DisplayName_Count
0x7440  ldarg.0
0x7441  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x7446  ldloc.s  9
0x7448  stelem.i4
0x7449  ldarga.s 1
0x744b  call     instance string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetMnemonicDisplayName()
0x7450  stloc.s  0xB
0x7452  ldc.i4.m1
0x7453  stloc.s  0xC
0x7455  ldloc.s  0xB
0x7457  brfalse.s loc_747E
0x7459  ldloc.s  0xB
0x745b  ldlen
0x745c  conv.i4
0x745d  stloc.s  0xC
0x745f  ldc.i4.0
0x7460  stloc.s  0xD
0x7462  ldc.i4.0
0x7463  stloc.s  0xD
0x7465  br.s     loc_7478
0x7467  ldarg.0
0x7468  ldloc.s  0xB
0x746a  ldloc.s  0xD
0x746c  ldelem.ref
0x746d  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteString(string value)
0x7472  ldloc.s  0xD
0x7474  ldc.i4.1
0x7475  add
0x7476  stloc.s  0xD
0x7478  ldloc.s  0xD
0x747a  ldloc.s  0xC
0x747c  blt.s    loc_7467
0x747e  ldarg.0
0x747f  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_MnemonicDisplayName_Count
0x7484  ldarg.0
0x7485  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x748a  ldloc.s  0xC
0x748c  stelem.i4
0x748d  ldarga.s 1
0x748f  call     instance string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetDescription()
0x7494  stloc.s  0xE
0x7496  ldc.i4.m1
0x7497  stloc.s  0xF
0x7499  ldloc.s  0xE
0x749b  brfalse.s loc_74C2
0x749d  ldloc.s  0xE
0x749f  ldlen
0x74a0  conv.i4
0x74a1  stloc.s  0xF
0x74a3  ldc.i4.0
0x74a4  stloc.s  0x10
0x74a6  ldc.i4.0
0x74a7  stloc.s  0x10
0x74a9  br.s     loc_74BC
0x74ab  ldarg.0
0x74ac  ldloc.s  0xE
0x74ae  ldloc.s  0x10
0x74b0  ldelem.ref
0x74b1  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteString(string value)
0x74b6  ldloc.s  0x10
0x74b8  ldc.i4.1
0x74b9  add
0x74ba  stloc.s  0x10
0x74bc  ldloc.s  0x10
0x74be  ldloc.s  0xF
0x74c0  blt.s    loc_74AB
0x74c2  ldarg.0
0x74c3  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_Description_Count
0x74c8  ldarg.0
0x74c9  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x74ce  ldloc.s  0xF
0x74d0  stelem.i4
0x74d1  ldarga.s 1
0x74d3  call     instance string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetLanguageIndependentName()
0x74d8  stloc.s  0x11
0x74da  ldc.i4.m1
0x74db  stloc.s  0x12
0x74dd  ldloc.s  0x11
0x74df  brfalse.s loc_7506
0x74e1  ldloc.s  0x11
0x74e3  ldlen
0x74e4  conv.i4
0x74e5  stloc.s  0x12
0x74e7  ldc.i4.0
0x74e8  stloc.s  0x13
0x74ea  ldc.i4.0
0x74eb  stloc.s  0x13
0x74ed  br.s     loc_7500
0x74ef  ldarg.0
0x74f0  ldloc.s  0x11
0x74f2  ldloc.s  0x13
0x74f4  ldelem.ref
0x74f5  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteString(string value)
0x74fa  ldloc.s  0x13
0x74fc  ldc.i4.1
0x74fd  add
0x74fe  stloc.s  0x13
0x7500  ldloc.s  0x13
0x7502  ldloc.s  0x12
0x7504  blt.s    loc_74EF
0x7506  ldarg.0
0x7507  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_LanguageIndependentName_Count
0x750c  ldarg.0
0x750d  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x7512  ldloc.s  0x12
0x7514  stelem.i4
0x7515  ldarga.s 1
0x7517  call     instance int32[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetImageIndex()
0x751c  stloc.s  0x14
0x751e  ldc.i4.m1
0x751f  stloc.s  0x15
0x7521  ldloc.s  0x14
0x7523  brfalse.s loc_7538
0x7525  ldarg.0
0x7526  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ImageIndex
0x752b  ldloc.s  0x14
0x752d  callvirt instance void Microsoft.ManagementConsole.Internal.Int32List::AddRange(int32[] items)
0x7532  ldloc.s  0x14
0x7534  ldlen
0x7535  conv.i4
0x7536  stloc.s  0x15
0x7538  ldarg.0
0x7539  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ImageIndex_Count
0x753e  ldarg.0
0x753f  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x7544  ldloc.s  0x15
0x7546  stelem.i4
0x7547  ldarga.s 1
0x7549  call     instance valuetype Microsoft.ManagementConsole.Internal.ActionStates[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetState()
0x754e  stloc.s  0x16
0x7550  ldc.i4.m1
0x7551  stloc.s  0x17
0x7553  ldloc.s  0x16
0x7555  brfalse.s loc_7581
0x7557  ldloc.s  0x16
0x7559  ldlen
0x755a  conv.i4
0x755b  stloc.s  0x17
0x755d  ldc.i4.0
0x755e  stloc.s  0x18
0x7560  ldc.i4.0
0x7561  stloc.s  0x18
0x7563  br.s     loc_757B
0x7565  ldarg.0
0x7566  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_State
0x756b  ldloc.s  0x16
0x756d  ldloc.s  0x18
0x756f  ldelem.i4
0x7570  callvirt instance void Microsoft.ManagementConsole.Internal.Int32List::Add(int32 item)
0x7575  ldloc.s  0x18
0x7577  ldc.i4.1
0x7578  add
0x7579  stloc.s  0x18
0x757b  ldloc.s  0x18
0x757d  ldloc.s  0x17
0x757f  blt.s    loc_7565
0x7581  ldarg.0
0x7582  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_State_Count
0x7587  ldarg.0
0x7588  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x758d  ldloc.s  0x17
0x758f  stelem.i4
0x7590  ldarga.s 1
0x7592  call     instance bool[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetExecuteSync()
0x7597  stloc.s  0x19
0x7599  ldc.i4.m1
0x759a  stloc.s  0x1A
0x759c  ldloc.s  0x19
0x759e  brfalse.s loc_75B3
0x75a0  ldarg.0
0x75a1  ldfld    class Microsoft.ManagementConsole.Internal.BooleanList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ExecuteSync
0x75a6  ldloc.s  0x19
0x75a8  callvirt instance void Microsoft.ManagementConsole.Internal.BooleanList::AddRange(bool[] items)
0x75ad  ldloc.s  0x19
0x75af  ldlen
0x75b0  conv.i4
0x75b1  stloc.s  0x1A
0x75b3  ldarg.0
0x75b4  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_Actions_ExecuteSync_Count
  ... truncated ...
```
