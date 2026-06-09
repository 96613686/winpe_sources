# System.Windows.Forms.Design.ControlCommandSet::OnKeySize

- ea: `0xa1160`
- end: `0xa171b`
- name: `System.Windows.Forms.Design.ControlCommandSet::OnKeySize`
- size: `1467`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x584f0`
- `0x8eec0`
- `0x98a50`
- `0x98ab0`
- `0x98ad0`
- `0x98d00`
- `0x98f50`
- `0x98fa0`
- `0xa1030`
- `0xa1160`
- `0xa29d0`
- `0xc2820`
- `0xc97e0`
- `0xe4a60`
- `0xe6930`
- `0xe73e0`
- `0xe8010`

## string_xrefs

- `0xa131a`: `DragDropSizeComponents`
- `0xa1342`: `DragDropSizeComponent`

## pseudocode

```c

```

## disassembly

```asm
0xa1160  ldarg.0
0xa1161  call     instance class [System]System.ComponentModel.Design.ISelectionService System.Windows.Forms.Design.CommandSet::get_SelectionService()
0xa1166  stloc.0
0xa1167  ldloc.0
0xa1168  brfalse  loc_A171A
0xa116d  ldloc.0
0xa116e  callvirt instance object [System]System.ComponentModel.Design.ISelectionService::get_PrimarySelection()
0xa1173  isinst   [System]System.ComponentModel.IComponent
0xa1178  stloc.1
0xa1179  ldloc.1
0xa117a  brfalse  loc_A171A
0xa117f  ldarg.0
0xa1180  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0xa1185  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa118a  callvirt instance object System.Windows.Forms.Design.CommandSet::GetService(class [mscorlib]System.Type serviceType)
0xa118f  castclass [System]System.ComponentModel.Design.IDesignerHost
0xa1194  stloc.2
0xa1195  ldloc.2
0xa1196  brfalse  loc_A171A
0xa119b  ldloc.2
0xa119c  ldloc.1
0xa119d  callvirt instance class [System]System.ComponentModel.Design.IDesigner [System]System.ComponentModel.Design.IDesignerHost::GetDesigner(class [System]System.ComponentModel.IComponent)
0xa11a2  isinst   System.Windows.Forms.Design.ControlDesigner
0xa11a7  stloc.3
0xa11a8  ldloc.3
0xa11a9  brfalse  loc_A171A
0xa11ae  ldloc.3
0xa11af  callvirt instance valuetype System.Windows.Forms.Design.SelectionRules System.Windows.Forms.Design.ControlDesigner::get_SelectionRules()
0xa11b4  ldc.i4   0x80000000
0xa11b9  and
0xa11ba  brtrue   loc_A171A
0xa11bf  ldc.i4.0
0xa11c0  stloc.s  4
0xa11c2  ldloc.1
0xa11c3  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xa11c8  ldstr    aDock// "Dock"
0xa11cd  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xa11d2  stloc.s  5
0xa11d4  ldloc.s  5
0xa11d6  brfalse.s loc_A11F6
0xa11d8  ldloc.s  5
0xa11da  ldloc.1
0xa11db  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0xa11e0  unbox.any [System.Windows.Forms]System.Windows.Forms.DockStyle
0xa11e5  stloc.s  0xD
0xa11e7  ldloc.s  0xD
0xa11e9  ldc.i4.2
0xa11ea  beq.s    loc_A11F3
0xa11ec  ldloc.s  0xD
0xa11ee  ldc.i4.4
0xa11ef  ceq
0xa11f1  br.s     loc_A11F4
0xa11f3  ldc.i4.1
0xa11f4  stloc.s  4
0xa11f6  ldc.i4   0x40000000
0xa11fb  stloc.s  6
0xa11fd  ldarg.1
0xa11fe  castclass [System]System.ComponentModel.Design.MenuCommand
0xa1203  callvirt instance class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.MenuCommand::get_CommandID()
0xa1208  stloc.s  7
0xa120a  ldc.i4.0
0xa120b  stloc.s  8
0xa120d  ldc.i4.0
0xa120e  stloc.s  9
0xa1210  ldc.i4.0
0xa1211  stloc.s  0xA
0xa1213  ldc.i4.0
0xa1214  stloc.s  0xB
0xa1216  ldloc.s  7
0xa1218  ldsfld   class [System]System.ComponentModel.Design.CommandID System.Windows.Forms.Design.MenuCommands::KeySizeHeightDecrease
0xa121d  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xa1222  brfalse.s loc_A1239
0xa1224  ldloc.s  4
0xa1226  brtrue.s loc_A122B
0xa1228  ldc.i4.m1
0xa1229  br.s     loc_A122C
0xa122b  ldc.i4.1
0xa122c  stloc.s  0xA
0xa122e  ldloc.s  6
0xa1230  ldc.i4.2
0xa1231  or
0xa1232  stloc.s  6
0xa1234  br       loc_A130D
0xa1239  ldloc.s  7
0xa123b  ldsfld   class [System]System.ComponentModel.Design.CommandID System.Windows.Forms.Design.MenuCommands::KeySizeHeightIncrease
0xa1240  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xa1245  brfalse.s loc_A125C
0xa1247  ldloc.s  4
0xa1249  brtrue.s loc_A124E
0xa124b  ldc.i4.1
0xa124c  br.s     loc_A124F
0xa124e  ldc.i4.m1
0xa124f  stloc.s  0xA
0xa1251  ldloc.s  6
0xa1253  ldc.i4.2
0xa1254  or
0xa1255  stloc.s  6
0xa1257  br       loc_A130D
0xa125c  ldloc.s  7
0xa125e  ldsfld   class [System]System.ComponentModel.Design.CommandID System.Windows.Forms.Design.MenuCommands::KeySizeWidthDecrease
0xa1263  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xa1268  brfalse.s loc_A127F
0xa126a  ldloc.s  4
0xa126c  brtrue.s loc_A1271
0xa126e  ldc.i4.m1
0xa126f  br.s     loc_A1272
0xa1271  ldc.i4.1
0xa1272  stloc.s  9
0xa1274  ldloc.s  6
0xa1276  ldc.i4.8
0xa1277  or
0xa1278  stloc.s  6
0xa127a  br       loc_A130D
0xa127f  ldloc.s  7
0xa1281  ldsfld   class [System]System.ComponentModel.Design.CommandID System.Windows.Forms.Design.MenuCommands::KeySizeWidthIncrease
0xa1286  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xa128b  brfalse.s loc_A129F
0xa128d  ldloc.s  4
0xa128f  brtrue.s loc_A1294
0xa1291  ldc.i4.1
0xa1292  br.s     loc_A1295
0xa1294  ldc.i4.m1
0xa1295  stloc.s  9
0xa1297  ldloc.s  6
0xa1299  ldc.i4.8
0xa129a  or
0xa129b  stloc.s  6
0xa129d  br.s     loc_A130D
0xa129f  ldloc.s  7
0xa12a1  ldsfld   class [System]System.ComponentModel.Design.CommandID System.Windows.Forms.Design.MenuCommands::KeyNudgeHeightDecrease
0xa12a6  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xa12ab  brfalse.s loc_A12BB
0xa12ad  ldc.i4.m1
0xa12ae  stloc.s  0xA
0xa12b0  ldc.i4.1
0xa12b1  stloc.s  8
0xa12b3  ldloc.s  6
0xa12b5  ldc.i4.2
0xa12b6  or
0xa12b7  stloc.s  6
0xa12b9  br.s     loc_A130D
0xa12bb  ldloc.s  7
0xa12bd  ldsfld   class [System]System.ComponentModel.Design.CommandID System.Windows.Forms.Design.MenuCommands::KeyNudgeHeightIncrease
0xa12c2  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xa12c7  brfalse.s loc_A12D7
0xa12c9  ldc.i4.1
0xa12ca  stloc.s  0xA
0xa12cc  ldc.i4.1
0xa12cd  stloc.s  8
0xa12cf  ldloc.s  6
0xa12d1  ldc.i4.2
0xa12d2  or
0xa12d3  stloc.s  6
0xa12d5  br.s     loc_A130D
0xa12d7  ldloc.s  7
0xa12d9  ldsfld   class [System]System.ComponentModel.Design.CommandID System.Windows.Forms.Design.MenuCommands::KeyNudgeWidthDecrease
0xa12de  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xa12e3  brfalse.s loc_A12F3
0xa12e5  ldc.i4.m1
0xa12e6  stloc.s  9
0xa12e8  ldc.i4.1
0xa12e9  stloc.s  8
0xa12eb  ldloc.s  6
0xa12ed  ldc.i4.8
0xa12ee  or
0xa12ef  stloc.s  6
0xa12f1  br.s     loc_A130D
0xa12f3  ldloc.s  7
0xa12f5  ldsfld   class [System]System.ComponentModel.Design.CommandID System.Windows.Forms.Design.MenuCommands::KeyNudgeWidthIncrease
0xa12fa  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xa12ff  brfalse.s loc_A130D
0xa1301  ldc.i4.1
0xa1302  stloc.s  9
0xa1304  ldc.i4.1
0xa1305  stloc.s  8
0xa1307  ldloc.s  6
0xa1309  ldc.i4.8
0xa130a  or
0xa130b  stloc.s  6
0xa130d  ldnull
0xa130e  stloc.s  0xC
0xa1310  ldloc.0
0xa1311  callvirt instance int32 [System]System.ComponentModel.Design.ISelectionService::get_SelectionCount()
0xa1316  ldc.i4.1
0xa1317  ble.s    loc_A1341
0xa1319  ldloc.2
0xa131a  ldstr    aDragdropsizeco// "DragDropSizeComponents"
0xa131f  ldc.i4.1
0xa1320  newarr   [mscorlib]System.Object
0xa1325  dup
0xa1326  ldc.i4.0
0xa1327  ldloc.0
0xa1328  callvirt instance int32 [System]System.ComponentModel.Design.ISelectionService::get_SelectionCount()
0xa132d  box      [mscorlib]System.Int32
0xa1332  stelem.ref
0xa1333  call     string System.Design.SR::GetString(string name, object[] args)
0xa1338  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0xa133d  stloc.s  0xC
0xa133f  br.s     loc_A1367
0xa1341  ldloc.2
0xa1342  ldstr    aDragdropsizeco_0// "DragDropSizeComponent"
0xa1347  ldc.i4.1
0xa1348  newarr   [mscorlib]System.Object
0xa134d  dup
0xa134e  ldc.i4.0
0xa134f  ldloc.1
0xa1350  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0xa1355  callvirt instance string [System]System.ComponentModel.ISite::get_Name()
0xa135a  stelem.ref
0xa135b  call     string System.Design.SR::GetString(string name, object[] args)
0xa1360  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0xa1365  stloc.s  0xC
0xa1367  nop
0xa1368  ldarg.0
0xa1369  call     instance class System.Windows.Forms.Design.Behavior.BehaviorService System.Windows.Forms.Design.CommandSet::get_BehaviorService()
0xa136e  brfalse  loc_A16EE
0xa1373  ldloc.1
0xa1374  isinst   [System.Windows.Forms]System.Windows.Forms.Control
0xa1379  stloc.s  0xE
0xa137b  ldarg.0
0xa137c  call     instance class System.Windows.Forms.Design.Behavior.BehaviorService System.Windows.Forms.Design.CommandSet::get_BehaviorService()
0xa1381  callvirt instance bool System.Windows.Forms.Design.Behavior.BehaviorService::get_UseSnapLines()
0xa1386  stloc.s  0xF
0xa1388  ldarg.0
0xa1389  ldfld    class System.Windows.Forms.Design.Behavior.DragAssistanceManager System.Windows.Forms.Design.CommandSet::dragManager
0xa138e  brfalse.s loc_A1396
0xa1390  ldarg.0
0xa1391  call     instance void System.Windows.Forms.Design.CommandSet::EndDragManager()
0xa1396  ldloc.s  8
0xa1398  ldloc.s  0xF
0xa139a  and
0xa139b  brfalse  loc_A1468
0xa13a0  ldloc.0
0xa13a1  callvirt instance class [mscorlib]System.Collections.ICollection [System]System.ComponentModel.Design.ISelectionService::GetSelectedComponents()
0xa13a6  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(class [mscorlib]System.Collections.ICollection)
0xa13ab  stloc.s  0x10
0xa13ad  ldarg.0
0xa13ae  ldloc.3
0xa13af  callvirt instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0xa13b4  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0xa13b9  ldloc.s  0x10
0xa13bb  newobj   instance void System.Windows.Forms.Design.Behavior.DragAssistanceManager::.ctor(class [mscorlib]System.IServiceProvider serviceProvider, class [mscorlib]System.Collections.ArrayList dragComponents)
0xa13c0  stfld    class System.Windows.Forms.Design.Behavior.DragAssistanceManager System.Windows.Forms.Design.CommandSet::dragManager
0xa13c5  ldarg.0
0xa13c6  ldloc.3
0xa13c7  callvirt instance valuetype System.Windows.Forms.Design.SelectionRules System.Windows.Forms.Design.ControlDesigner::get_SelectionRules()
0xa13cc  ldloc.s  0xE
0xa13ce  ldloc.s  9
0xa13d0  ldloc.s  0xA
0xa13d2  call     instance class [mscorlib]System.Collections.ArrayList System.Windows.Forms.Design.ControlCommandSet::GenerateSnapLines(valuetype System.Windows.Forms.Design.SelectionRules rules, class [System.Windows.Forms]System.Windows.Forms.Control primaryControl, int32 directionOffsetX, int32 directionOffsetY)
0xa13d7  stloc.s  0x11
0xa13d9  ldarg.0
0xa13da  ldfld    class System.Windows.Forms.Design.Behavior.DragAssistanceManager System.Windows.Forms.Design.CommandSet::dragManager
0xa13df  ldloc.s  0xE
0xa13e1  ldloc.s  0x11
0xa13e3  ldloc.s  9
0xa13e5  ldloc.s  0xA
0xa13e7  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0xa13ec  callvirt instance valuetype [System.Drawing]System.Drawing.Point System.Windows.Forms.Design.Behavior.DragAssistanceManager::OffsetToNearestSnapLocation(class [System.Windows.Forms]System.Windows.Forms.Control targetControl, class [mscorlib]System.Collections.IList targetSnaplines, valuetype [System.Drawing]System.Drawing.Point directionOffset)
0xa13f1  stloc.s  0x12
0xa13f3  ldloc.s  0xE
0xa13f5  callvirt instance valuetype [System.Drawing]System.Drawing.Size [System.Windows.Forms]System.Windows.Forms.Control::get_Size()
0xa13fa  stloc.s  0x13
0xa13fc  ldloc.s  0x13
0xa13fe  ldloca.s 0x12
0xa1400  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0xa1405  ldloca.s 0x12
0xa1407  call     instance int32 [System.Drawing]System.Drawing.Point::get_Y()
0xa140c  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0xa1411  call     valuetype [System.Drawing]System.Drawing.Size [System.Drawing]System.Drawing.Size::op_Addition(valuetype [System.Drawing]System.Drawing.Size, valuetype [System.Drawing]System.Drawing.Size)
0xa1416  stloc.s  0x13
0xa1418  ldloca.s 0x13
0xa141a  call     instance int32 [System.Drawing]System.Drawing.Size::get_Width()
0xa141f  ldc.i4.0
0xa1420  ble.s    loc_A142C
0xa1422  ldloca.s 0x13
0xa1424  call     instance int32 [System.Drawing]System.Drawing.Size::get_Height()
0xa1429  ldc.i4.0
0xa142a  bgt.s    loc_A143A
0xa142c  ldc.i4.0
0xa142d  stloc.s  9
0xa142f  ldc.i4.0
0xa1430  stloc.s  0xA
0xa1432  ldarg.0
0xa1433  call     instance void System.Windows.Forms.Design.CommandSet::EndDragManager()
0xa1438  br.s     loc_A144C
0xa143a  ldloca.s 0x12
0xa143c  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0xa1441  stloc.s  9
0xa1443  ldloca.s 0x12
0xa1445  call     instance int32 [System.Drawing]System.Drawing.Point::get_Y()
0xa144a  stloc.s  0xA
0xa144c  ldloc.s  0xE
0xa144e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0xa1453  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::get_IsMirrored()
0xa1458  brfalse  loc_A15AC
0xa145d  ldloc.s  9
0xa145f  ldc.i4.m1
0xa1460  mul
0xa1461  stloc.s  9
  ... truncated ...
```
