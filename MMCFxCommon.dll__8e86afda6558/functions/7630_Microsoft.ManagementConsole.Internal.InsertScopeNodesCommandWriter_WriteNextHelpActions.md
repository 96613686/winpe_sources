# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextHelpActions

- ea: `0x7630`
- end: `0x7907`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextHelpActions`
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
- `0x7630`
- `0x8320`
- `0x8530`
- `0x8560`

## pseudocode

```c

```

## disassembly

```asm
0x7630  ldarga.s 1
0x7632  call     instance int32[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetId()
0x7637  stloc.0
0x7638  ldc.i4.m1
0x7639  stloc.1
0x763a  ldloc.0
0x763b  brfalse.s loc_764D
0x763d  ldarg.0
0x763e  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_Id
0x7643  ldloc.0
0x7644  callvirt instance void Microsoft.ManagementConsole.Internal.Int32List::AddRange(int32[] items)
0x7649  ldloc.0
0x764a  ldlen
0x764b  conv.i4
0x764c  stloc.1
0x764d  ldarg.0
0x764e  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_Id_Count
0x7653  ldarg.0
0x7654  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x7659  ldloc.1
0x765a  stelem.i4
0x765b  ldarga.s 1
0x765d  call     instance valuetype Microsoft.ManagementConsole.Internal.ActionsPaneRootItemType[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetItemType()
0x7662  stloc.2
0x7663  ldc.i4.m1
0x7664  stloc.3
0x7665  ldloc.2
0x7666  brfalse.s loc_768E
0x7668  ldloc.2
0x7669  ldlen
0x766a  conv.i4
0x766b  stloc.3
0x766c  ldc.i4.0
0x766d  stloc.s  4
0x766f  ldc.i4.0
0x7670  stloc.s  4
0x7672  br.s     loc_7689
0x7674  ldarg.0
0x7675  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_ItemType
0x767a  ldloc.2
0x767b  ldloc.s  4
0x767d  ldelem.i4
0x767e  callvirt instance void Microsoft.ManagementConsole.Internal.Int32List::Add(int32 item)
0x7683  ldloc.s  4
0x7685  ldc.i4.1
0x7686  add
0x7687  stloc.s  4
0x7689  ldloc.s  4
0x768b  ldloc.3
0x768c  blt.s    loc_7674
0x768e  ldarg.0
0x768f  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_ItemType_Count
0x7694  ldarg.0
0x7695  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x769a  ldloc.3
0x769b  stelem.i4
0x769c  ldarga.s 1
0x769e  call     instance valuetype Microsoft.ManagementConsole.Internal.ActionsInsertionLocation[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetInsertionLocation()
0x76a3  stloc.s  5
0x76a5  ldc.i4.m1
0x76a6  stloc.s  6
0x76a8  ldloc.s  5
0x76aa  brfalse.s loc_76D6
0x76ac  ldloc.s  5
0x76ae  ldlen
0x76af  conv.i4
0x76b0  stloc.s  6
0x76b2  ldc.i4.0
0x76b3  stloc.s  7
0x76b5  ldc.i4.0
0x76b6  stloc.s  7
0x76b8  br.s     loc_76D0
0x76ba  ldarg.0
0x76bb  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_InsertionLocation
0x76c0  ldloc.s  5
0x76c2  ldloc.s  7
0x76c4  ldelem.i4
0x76c5  callvirt instance void Microsoft.ManagementConsole.Internal.Int32List::Add(int32 item)
0x76ca  ldloc.s  7
0x76cc  ldc.i4.1
0x76cd  add
0x76ce  stloc.s  7
0x76d0  ldloc.s  7
0x76d2  ldloc.s  6
0x76d4  blt.s    loc_76BA
0x76d6  ldarg.0
0x76d7  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_InsertionLocation_Count
0x76dc  ldarg.0
0x76dd  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x76e2  ldloc.s  6
0x76e4  stelem.i4
0x76e5  ldarga.s 1
0x76e7  call     instance string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetDisplayName()
0x76ec  stloc.s  8
0x76ee  ldc.i4.m1
0x76ef  stloc.s  9
0x76f1  ldloc.s  8
0x76f3  brfalse.s loc_771A
0x76f5  ldloc.s  8
0x76f7  ldlen
0x76f8  conv.i4
0x76f9  stloc.s  9
0x76fb  ldc.i4.0
0x76fc  stloc.s  0xA
0x76fe  ldc.i4.0
0x76ff  stloc.s  0xA
0x7701  br.s     loc_7714
0x7703  ldarg.0
0x7704  ldloc.s  8
0x7706  ldloc.s  0xA
0x7708  ldelem.ref
0x7709  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteString(string value)
0x770e  ldloc.s  0xA
0x7710  ldc.i4.1
0x7711  add
0x7712  stloc.s  0xA
0x7714  ldloc.s  0xA
0x7716  ldloc.s  9
0x7718  blt.s    loc_7703
0x771a  ldarg.0
0x771b  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_DisplayName_Count
0x7720  ldarg.0
0x7721  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x7726  ldloc.s  9
0x7728  stelem.i4
0x7729  ldarga.s 1
0x772b  call     instance string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetMnemonicDisplayName()
0x7730  stloc.s  0xB
0x7732  ldc.i4.m1
0x7733  stloc.s  0xC
0x7735  ldloc.s  0xB
0x7737  brfalse.s loc_775E
0x7739  ldloc.s  0xB
0x773b  ldlen
0x773c  conv.i4
0x773d  stloc.s  0xC
0x773f  ldc.i4.0
0x7740  stloc.s  0xD
0x7742  ldc.i4.0
0x7743  stloc.s  0xD
0x7745  br.s     loc_7758
0x7747  ldarg.0
0x7748  ldloc.s  0xB
0x774a  ldloc.s  0xD
0x774c  ldelem.ref
0x774d  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteString(string value)
0x7752  ldloc.s  0xD
0x7754  ldc.i4.1
0x7755  add
0x7756  stloc.s  0xD
0x7758  ldloc.s  0xD
0x775a  ldloc.s  0xC
0x775c  blt.s    loc_7747
0x775e  ldarg.0
0x775f  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_MnemonicDisplayName_Count
0x7764  ldarg.0
0x7765  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x776a  ldloc.s  0xC
0x776c  stelem.i4
0x776d  ldarga.s 1
0x776f  call     instance string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetDescription()
0x7774  stloc.s  0xE
0x7776  ldc.i4.m1
0x7777  stloc.s  0xF
0x7779  ldloc.s  0xE
0x777b  brfalse.s loc_77A2
0x777d  ldloc.s  0xE
0x777f  ldlen
0x7780  conv.i4
0x7781  stloc.s  0xF
0x7783  ldc.i4.0
0x7784  stloc.s  0x10
0x7786  ldc.i4.0
0x7787  stloc.s  0x10
0x7789  br.s     loc_779C
0x778b  ldarg.0
0x778c  ldloc.s  0xE
0x778e  ldloc.s  0x10
0x7790  ldelem.ref
0x7791  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteString(string value)
0x7796  ldloc.s  0x10
0x7798  ldc.i4.1
0x7799  add
0x779a  stloc.s  0x10
0x779c  ldloc.s  0x10
0x779e  ldloc.s  0xF
0x77a0  blt.s    loc_778B
0x77a2  ldarg.0
0x77a3  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_Description_Count
0x77a8  ldarg.0
0x77a9  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x77ae  ldloc.s  0xF
0x77b0  stelem.i4
0x77b1  ldarga.s 1
0x77b3  call     instance string[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetLanguageIndependentName()
0x77b8  stloc.s  0x11
0x77ba  ldc.i4.m1
0x77bb  stloc.s  0x12
0x77bd  ldloc.s  0x11
0x77bf  brfalse.s loc_77E6
0x77c1  ldloc.s  0x11
0x77c3  ldlen
0x77c4  conv.i4
0x77c5  stloc.s  0x12
0x77c7  ldc.i4.0
0x77c8  stloc.s  0x13
0x77ca  ldc.i4.0
0x77cb  stloc.s  0x13
0x77cd  br.s     loc_77E0
0x77cf  ldarg.0
0x77d0  ldloc.s  0x11
0x77d2  ldloc.s  0x13
0x77d4  ldelem.ref
0x77d5  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteString(string value)
0x77da  ldloc.s  0x13
0x77dc  ldc.i4.1
0x77dd  add
0x77de  stloc.s  0x13
0x77e0  ldloc.s  0x13
0x77e2  ldloc.s  0x12
0x77e4  blt.s    loc_77CF
0x77e6  ldarg.0
0x77e7  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_LanguageIndependentName_Count
0x77ec  ldarg.0
0x77ed  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x77f2  ldloc.s  0x12
0x77f4  stelem.i4
0x77f5  ldarga.s 1
0x77f7  call     instance int32[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetImageIndex()
0x77fc  stloc.s  0x14
0x77fe  ldc.i4.m1
0x77ff  stloc.s  0x15
0x7801  ldloc.s  0x14
0x7803  brfalse.s loc_7818
0x7805  ldarg.0
0x7806  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_ImageIndex
0x780b  ldloc.s  0x14
0x780d  callvirt instance void Microsoft.ManagementConsole.Internal.Int32List::AddRange(int32[] items)
0x7812  ldloc.s  0x14
0x7814  ldlen
0x7815  conv.i4
0x7816  stloc.s  0x15
0x7818  ldarg.0
0x7819  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_ImageIndex_Count
0x781e  ldarg.0
0x781f  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x7824  ldloc.s  0x15
0x7826  stelem.i4
0x7827  ldarga.s 1
0x7829  call     instance valuetype Microsoft.ManagementConsole.Internal.ActionStates[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetState()
0x782e  stloc.s  0x16
0x7830  ldc.i4.m1
0x7831  stloc.s  0x17
0x7833  ldloc.s  0x16
0x7835  brfalse.s loc_7861
0x7837  ldloc.s  0x16
0x7839  ldlen
0x783a  conv.i4
0x783b  stloc.s  0x17
0x783d  ldc.i4.0
0x783e  stloc.s  0x18
0x7840  ldc.i4.0
0x7841  stloc.s  0x18
0x7843  br.s     loc_785B
0x7845  ldarg.0
0x7846  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_State
0x784b  ldloc.s  0x16
0x784d  ldloc.s  0x18
0x784f  ldelem.i4
0x7850  callvirt instance void Microsoft.ManagementConsole.Internal.Int32List::Add(int32 item)
0x7855  ldloc.s  0x18
0x7857  ldc.i4.1
0x7858  add
0x7859  stloc.s  0x18
0x785b  ldloc.s  0x18
0x785d  ldloc.s  0x17
0x785f  blt.s    loc_7845
0x7861  ldarg.0
0x7862  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_State_Count
0x7867  ldarg.0
0x7868  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_currentIndex
0x786d  ldloc.s  0x17
0x786f  stelem.i4
0x7870  ldarga.s 1
0x7872  call     instance bool[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::GetExecuteSync()
0x7877  stloc.s  0x19
0x7879  ldc.i4.m1
0x787a  stloc.s  0x1A
0x787c  ldloc.s  0x19
0x787e  brfalse.s loc_7893
0x7880  ldarg.0
0x7881  ldfld    class Microsoft.ManagementConsole.Internal.BooleanList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_ExecuteSync
0x7886  ldloc.s  0x19
0x7888  callvirt instance void Microsoft.ManagementConsole.Internal.BooleanList::AddRange(bool[] items)
0x788d  ldloc.s  0x19
0x788f  ldlen
0x7890  conv.i4
0x7891  stloc.s  0x1A
0x7893  ldarg.0
0x7894  ldfld    int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_HelpActions_ExecuteSync_Count
  ... truncated ...
```
