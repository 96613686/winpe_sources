# Microsoft.EventViewer.SnapIn.MMCEventsResultView::GetAction

- ea: `0x5d60`
- end: `0x6220`
- name: `Microsoft.EventViewer.SnapIn.MMCEventsResultView::GetAction`
- size: `1216`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `broker_com_uri`

## callees

- `0x2a80`
- `0x2ad0`
- `0x2ce0`
- `0x3d90`
- `0x5d60`
- `0x6220`
- `0x6270`
- `0x62c0`
- `0x6310`
- `0x6360`
- `0x63b0`
- `0x8010`
- `0x8380`
- `0x8570`
- `0x8680`
- `0x9070`
- `0x9f30`
- `0x9f50`
- `0xa2b0`
- `0xa2d0`
- `0xa2f0`
- `0xa310`

## string_xrefs

- `0x603f`: `ActionCopyToClipboard`
- `0x6050`: `ActionCopyToClipboardDesc`
- `0x61b5`: `This action for result control should not be coming:`

## pseudocode

```c

```

## disassembly

```asm
0x5d60  ldnull
0x5d61  stloc.0
0x5d62  ldarg.2
0x5d63  ldnull
0x5d64  stind.ref
0x5d65  ldc.i4.0
0x5d66  stloc.1
0x5d67  ldarg.1
0x5d68  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x5d6d  stloc.3
0x5d6e  ldloc.3
0x5d6f  ldc.i4.3
0x5d70  sub
0x5d71  switch   loc_5DEC, loc_61B5, loc_6161, loc_61B5, loc_61B5, loc_5DFD, loc_61B5, loc_61E8, loc_6124, loc_61B5, loc_61B5, loc_5E14, loc_5E5F
0x5daa  ldloc.3
0x5dab  ldc.i4.s 0x13
0x5dad  sub
0x5dae  switch   loc_6019, loc_61B5, loc_61B5, loc_61B5, loc_61B5, loc_616F, loc_61B5, loc_5F3C, loc_6199, loc_617D, loc_618B
0x5ddf  ldloc.3
0x5de0  ldc.i4.s 0x21
0x5de2  beq      loc_61A7
0x5de7  br       loc_61B5
0x5dec  ldarg.1
0x5ded  call     class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase Microsoft.EventViewer.SnapIn.ViewerRootNode::GetPreviewAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x5df2  stloc.0
0x5df3  ldarg.2
0x5df4  ldloc.0
0x5df5  stind.ref
0x5df6  ldc.i4.1
0x5df7  stloc.1
0x5df8  br       loc_61E8
0x5dfd  ldarg.1
0x5dfe  call     class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase Microsoft.EventViewer.SnapIn.ViewerRootNode::GetEventPropertiesAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x5e03  stloc.0
0x5e04  ldloc.0
0x5e05  brfalse  loc_61E8
0x5e0a  ldarg.2
0x5e0b  ldloc.0
0x5e0c  stind.ref
0x5e0d  ldc.i4.1
0x5e0e  stloc.1
0x5e0f  br       loc_61E8
0x5e14  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SyncAction::.ctor()
0x5e19  stloc.0
0x5e1a  ldloc.0
0x5e1b  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddTaskToEventDesc()
0x5e20  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_Description(string)
0x5e25  ldloc.0
0x5e26  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionAddTaskToEvent()
0x5e2b  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x5e30  ldloc.0
0x5e31  ldarg.1
0x5e32  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x5e37  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndex(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x5e3c  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x5e41  ldarg.1
0x5e42  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x5e47  ldloca.s 0
0x5e49  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& action)
0x5e4e  ldloc.0
0x5e4f  ldarg.1
0x5e50  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x5e55  ldarg.2
0x5e56  ldloc.0
0x5e57  stind.ref
0x5e58  ldc.i4.1
0x5e59  stloc.1
0x5e5a  br       loc_61E8
0x5e5f  ldarg.1
0x5e60  callvirt instance class [mscorlib]System.Collections.IDictionary [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Items()
0x5e65  brfalse  loc_61E8
0x5e6a  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionGroup::.ctor()
0x5e6f  stloc.s  4
0x5e71  ldloc.s  4
0x5e73  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionSortDesc()
0x5e78  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_Description(string)
0x5e7d  ldloc.s  4
0x5e7f  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionSort()
0x5e84  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x5e89  ldloc.s  4
0x5e8b  ldarg.1
0x5e8c  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x5e91  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndex(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x5e96  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x5e9b  ldloc.s  4
0x5e9d  ldarg.1
0x5e9e  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x5ea3  ldarg.1
0x5ea4  callvirt instance class [mscorlib]System.Collections.IDictionary [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Items()
0x5ea9  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x5eae  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x5eb3  stloc.s  6
0x5eb5  br.s     loc_5F11
0x5eb7  ldloc.s  6
0x5eb9  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5ebe  castclass [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction
0x5ec3  stloc.s  7
0x5ec5  ldloc.s  7
0x5ec7  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x5ecc  ldc.i4.2
0x5ecd  beq.s    loc_5F11
0x5ecf  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Action::.ctor()
0x5ed4  stloc.s  5
0x5ed6  ldloc.s  5
0x5ed8  ldloc.s  7
0x5eda  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Name()
0x5edf  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x5ee4  ldarg.1
0x5ee5  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x5eea  ldloca.s 5
0x5eec  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& action)
0x5ef1  ldloc.s  5
0x5ef3  ldloc.s  7
0x5ef5  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x5efa  ldarg.0
0x5efb  ldloca.s 5
0x5efd  call     instance void Microsoft.EventViewer.SnapIn.FormControlBase::SetTriggeredForAction(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& actBase)
0x5f02  ldloc.s  4
0x5f04  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionGroup::get_Items()
0x5f09  ldloc.s  5
0x5f0b  callvirt instance int32 [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection::Add(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem)
0x5f10  pop
0x5f11  ldloc.s  6
0x5f13  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5f18  brtrue.s loc_5EB7
0x5f1a  leave.s  loc_5F31
0x5f1c  ldloc.s  6
0x5f1e  isinst   [mscorlib]System.IDisposable
0x5f23  stloc.s  8
0x5f25  ldloc.s  8
0x5f27  brfalse.s loc_5F30
0x5f29  ldloc.s  8
0x5f2b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5f30  endfinally
0x5f31  ldarg.2
0x5f32  ldloc.s  4
0x5f34  stind.ref
0x5f35  ldc.i4.1
0x5f36  stloc.1
0x5f37  br       loc_61E8
0x5f3c  ldarg.1
0x5f3d  callvirt instance class [mscorlib]System.Collections.IDictionary [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Items()
0x5f42  brfalse  loc_61E8
0x5f47  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionGroup::.ctor()
0x5f4c  stloc.s  9
0x5f4e  ldloc.s  9
0x5f50  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionGroupDesc()
0x5f55  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_Description(string)
0x5f5a  ldloc.s  9
0x5f5c  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ActionGroup()
0x5f61  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x5f66  ldloc.s  9
0x5f68  ldarg.1
0x5f69  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x5f6e  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndex(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x5f73  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x5f78  ldloc.s  9
0x5f7a  ldarg.1
0x5f7b  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x5f80  ldarg.1
0x5f81  callvirt instance class [mscorlib]System.Collections.IDictionary [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Items()
0x5f86  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x5f8b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x5f90  stloc.s  6
0x5f92  br.s     loc_5FEE
0x5f94  ldloc.s  6
0x5f96  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5f9b  castclass [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction
0x5fa0  stloc.s  0xB
0x5fa2  ldloc.s  0xB
0x5fa4  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x5fa9  ldc.i4.2
0x5faa  beq.s    loc_5FEE
0x5fac  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Action::.ctor()
0x5fb1  stloc.s  0xA
0x5fb3  ldloc.s  0xA
0x5fb5  ldloc.s  0xB
0x5fb7  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Name()
0x5fbc  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x5fc1  ldarg.1
0x5fc2  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x5fc7  ldloca.s 0xA
0x5fc9  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& action)
0x5fce  ldloc.s  0xA
0x5fd0  ldloc.s  0xB
0x5fd2  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x5fd7  ldarg.0
0x5fd8  ldloca.s 0xA
0x5fda  call     instance void Microsoft.EventViewer.SnapIn.FormControlBase::SetTriggeredForAction(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& actBase)
0x5fdf  ldloc.s  9
0x5fe1  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionGroup::get_Items()
0x5fe6  ldloc.s  0xA
0x5fe8  callvirt instance int32 [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection::Add(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem)
0x5fed  pop
0x5fee  ldloc.s  6
0x5ff0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5ff5  brtrue.s loc_5F94
0x5ff7  leave.s  loc_600E
0x5ff9  ldloc.s  6
0x5ffb  isinst   [mscorlib]System.IDisposable
0x6000  stloc.s  8
0x6002  ldloc.s  8
0x6004  brfalse.s loc_600D
0x6006  ldloc.s  8
0x6008  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x600d  endfinally
0x600e  ldarg.2
0x600f  ldloc.s  9
0x6011  stind.ref
0x6012  ldc.i4.1
0x6013  stloc.1
0x6014  br       loc_61E8
0x6019  ldarg.1
0x601a  callvirt instance class [mscorlib]System.Collections.IDictionary [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Items()
0x601f  brfalse  loc_61E8
0x6024  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionGroup::.ctor()
0x6029  stloc.s  0xC
0x602b  ldloc.s  0xC
0x602d  ldarg.1
0x602e  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x6033  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndex(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x6038  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x603d  ldloc.s  0xC
0x603f  ldstr    aActioncopytocl// "ActionCopyToClipboard"
0x6044  call     string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string)
0x6049  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x604e  ldloc.s  0xC
0x6050  ldstr    aActioncopytocl_0// "ActionCopyToClipboardDesc"
0x6055  call     string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string)
0x605a  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_Description(string)
0x605f  ldloc.s  0xC
0x6061  ldarg.1
0x6062  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x6067  ldarg.1
0x6068  callvirt instance class [mscorlib]System.Collections.IDictionary [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Items()
0x606d  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x6072  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x6077  stloc.s  6
0x6079  br.s     loc_60F6
0x607b  ldloc.s  6
0x607d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6082  castclass [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction
0x6087  stloc.s  0xE
0x6089  ldloc.s  0xE
0x608b  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x6090  ldc.i4.2
0x6091  beq.s    loc_60F6
0x6093  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Action::.ctor()
0x6098  stloc.s  0xD
0x609a  ldloc.s  0xD
0x609c  ldloc.s  0xE
0x609e  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_DisplayName()
0x60a3  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x60a8  ldloc.s  0xD
0x60aa  ldloc.s  0xE
0x60ac  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Description()
0x60b1  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_Description(string)
0x60b6  ldloc.s  0xD
0x60b8  ldloc.s  0xE
0x60ba  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x60bf  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndex(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x60c4  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x60c9  ldarg.1
0x60ca  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x60cf  ldloca.s 0xD
0x60d1  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& action)
0x60d6  ldloc.s  0xD
0x60d8  ldloc.s  0xE
0x60da  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x60df  ldarg.0
0x60e0  ldloca.s 0xD
0x60e2  call     instance void Microsoft.EventViewer.SnapIn.FormControlBase::SetTriggeredForAction(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& actBase)
0x60e7  ldloc.s  0xC
0x60e9  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionGroup::get_Items()
0x60ee  ldloc.s  0xD
0x60f0  callvirt instance int32 [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection::Add(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem)
0x60f5  pop
0x60f6  ldloc.s  6
0x60f8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x60fd  brtrue   loc_607B
0x6102  leave.s  loc_6119
0x6104  ldloc.s  6
0x6106  isinst   [mscorlib]System.IDisposable
0x610b  stloc.s  8
0x610d  ldloc.s  8
0x610f  brfalse.s loc_6118
0x6111  ldloc.s  8
0x6113  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6118  endfinally
0x6119  ldarg.2
0x611a  ldloc.s  0xC
0x611c  stind.ref
0x611d  ldc.i4.1
0x611e  stloc.1
0x611f  br       loc_61E8
0x6124  ldarg.0
0x6125  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x612a  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x612f  castclass Microsoft.EventViewer.SnapIn.MMCEventsNode
0x6134  stloc.2
  ... truncated ...
```
