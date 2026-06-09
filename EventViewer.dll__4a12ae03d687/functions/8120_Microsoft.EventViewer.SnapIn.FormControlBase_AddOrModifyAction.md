# Microsoft.EventViewer.SnapIn.FormControlBase::AddOrModifyAction

- ea: `0x8120`
- end: `0x8377`
- name: `Microsoft.EventViewer.SnapIn.FormControlBase::AddOrModifyAction`
- size: `599`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x4d70`
- `0x57a0`
- `0x7cf0`
- `0x83f0`
- `0x97f0`

## callees

- `0x8010`
- `0x80b0`
- `0x8120`
- `0x8570`
- `0x8630`
- `0x9070`

## pseudocode

```c

```

## disassembly

```asm
0x8120  ldc.i4.0
0x8121  stloc.2
0x8122  ldarg.0
0x8123  ldarg.1
0x8124  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection Microsoft.EventViewer.SnapIn.FormControlBase::GetActionPaneForAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x8129  stloc.3
0x812a  ldarg.0
0x812b  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.EventViewer.SnapIn.FormControlBase::actions
0x8130  ldarg.1
0x8131  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x8136  box      [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers
0x813b  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x8140  brfalse  loc_8315
0x8145  ldarg.0
0x8146  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.EventViewer.SnapIn.FormControlBase::actions
0x814b  ldarg.1
0x814c  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x8151  box      [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers
0x8156  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x815b  castclass [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem
0x8160  stloc.0
0x8161  ldloc.3
0x8162  ldloc.0
0x8163  callvirt instance int32 [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection::IndexOf(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem)
0x8168  stloc.s  4
0x816a  ldarg.1
0x816b  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x8170  ldc.i4.2
0x8171  bne.un.s loc_8180
0x8173  ldloc.s  4
0x8175  ldc.i4.m1
0x8176  beq.s    loc_8180
0x8178  ldloc.3
0x8179  ldloc.s  4
0x817b  callvirt instance void [mscorlib]System.Collections.CollectionBase::RemoveAt(int32)
0x8180  ldarg.1
0x8181  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x8186  ldc.i4.2
0x8187  beq      loc_8376
0x818c  ldloc.0
0x818d  ldarg.1
0x818e  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x8193  ldloc.0
0x8194  isinst   [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase
0x8199  stloc.1
0x819a  ldloc.1
0x819b  brfalse.s loc_81D0
0x819d  ldloc.1
0x819e  ldarg.1
0x819f  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Checked()
0x81a4  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase::set_Checked(bool)
0x81a9  ldarg.1
0x81aa  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x81af  ldloc.1
0x81b0  call     bool Microsoft.EventViewer.SnapIn.ViewerCommon::ActionStatusChanged(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase action)
0x81b5  stloc.2
0x81b6  ldloc.2
0x81b7  brfalse  loc_82C1
0x81bc  ldarg.1
0x81bd  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x81c2  ldloca.s 1
0x81c4  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& action)
0x81c9  ldloc.1
0x81ca  stloc.0
0x81cb  br       loc_82C1
0x81d0  ldloc.0
0x81d1  isinst   [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionGroup
0x81d6  stloc.s  5
0x81d8  ldloc.s  5
0x81da  brfalse  loc_82C1
0x81df  ldarg.1
0x81e0  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x81e5  ldc.i4.2
0x81e6  beq      loc_82C1
0x81eb  ldc.i4.0
0x81ec  stloc.s  7
0x81ee  br       loc_82AB
0x81f3  ldloc.s  5
0x81f5  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionGroup::get_Items()
0x81fa  ldloc.s  7
0x81fc  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection::get_Item(int32)
0x8201  isinst   [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase
0x8206  stloc.s  6
0x8208  ldloc.s  6
0x820a  brfalse  loc_82A5
0x820f  ldarg.1
0x8210  callvirt instance class [mscorlib]System.Collections.IDictionary [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Items()
0x8215  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x821a  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x821f  stloc.s  8
0x8221  br.s     loc_8257
0x8223  ldloc.s  8
0x8225  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x822a  castclass [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction
0x822f  stloc.s  9
0x8231  ldloc.s  6
0x8233  callvirt instance string [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::get_DisplayName()
0x8238  ldloc.s  9
0x823a  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Name()
0x823f  ldc.i4.0
0x8240  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x8245  brfalse.s loc_8257
0x8247  ldloc.s  6
0x8249  ldloc.s  9
0x824b  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Checked()
0x8250  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase::set_Checked(bool)
0x8255  leave.s  loc_8277
0x8257  ldloc.s  8
0x8259  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x825e  brtrue.s loc_8223
0x8260  leave.s  loc_8277
0x8262  ldloc.s  8
0x8264  isinst   [mscorlib]System.IDisposable
0x8269  stloc.s  0xA
0x826b  ldloc.s  0xA
0x826d  brfalse.s loc_8276
0x826f  ldloc.s  0xA
0x8271  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8276  endfinally
0x8277  ldarg.1
0x8278  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x827d  ldloc.s  6
0x827f  call     bool Microsoft.EventViewer.SnapIn.ViewerCommon::ActionStatusChanged(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase action)
0x8284  stloc.2
0x8285  ldloc.2
0x8286  brfalse.s loc_82A5
0x8288  ldarg.1
0x8289  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x828e  ldloca.s 6
0x8290  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& action)
0x8295  ldloc.s  5
0x8297  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionGroup::get_Items()
0x829c  ldloc.s  7
0x829e  ldloc.s  6
0x82a0  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection::set_Item(int32, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem)
0x82a5  ldloc.s  7
0x82a7  ldc.i4.1
0x82a8  add
0x82a9  stloc.s  7
0x82ab  ldloc.s  7
0x82ad  ldloc.s  5
0x82af  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionGroup::get_Items()
0x82b4  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x82b9  blt      loc_81F3
0x82be  ldloc.s  5
0x82c0  stloc.0
0x82c1  ldloc.0
0x82c2  isinst   [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase
0x82c7  stloc.1
0x82c8  ldloc.1
0x82c9  brfalse.s loc_82DE
0x82cb  ldloc.1
0x82cc  ldarg.1
0x82cd  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x82d2  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndexForAction(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x82d7  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x82dc  ldloc.1
0x82dd  stloc.0
0x82de  ldarg.0
0x82df  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.EventViewer.SnapIn.FormControlBase::actions
0x82e4  ldarg.1
0x82e5  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x82ea  box      [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers
0x82ef  ldloc.0
0x82f0  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x82f5  ldloc.2
0x82f6  brfalse.s loc_8307
0x82f8  ldloc.s  4
0x82fa  ldc.i4.0
0x82fb  blt.s    loc_8307
0x82fd  ldloc.3
0x82fe  ldloc.s  4
0x8300  ldloc.0
0x8301  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection::set_Item(int32, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem)
0x8306  ret
0x8307  ldloc.s  4
0x8309  ldc.i4.0
0x830a  bge.s    loc_8376
0x830c  ldloc.3
0x830d  ldloc.0
0x830e  callvirt instance int32 [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection::Add(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem)
0x8313  pop
0x8314  ret
0x8315  ldarg.1
0x8316  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x831b  ldc.i4.s 0x10
0x831d  bne.un.s loc_8340
0x831f  ldarg.0
0x8320  ldfld    bool Microsoft.EventViewer.SnapIn.FormControlBase::actionsInitialized
0x8325  brtrue.s loc_8340
0x8327  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionSeparator::.ctor()
0x832c  stloc.s  0xB
0x832e  ldloc.s  0xB
0x8330  ldarg.1
0x8331  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x8336  ldloc.3
0x8337  ldloc.s  0xB
0x8339  callvirt instance int32 [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection::Add(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem)
0x833e  pop
0x833f  ret
0x8340  ldarg.0
0x8341  ldarg.1
0x8342  ldloca.s 0
0x8344  callvirt instance bool Microsoft.EventViewer.SnapIn.FormControlBase::GetAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action, [out] class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem& actionOut)
0x8349  brfalse.s loc_8376
0x834b  ldloc.0
0x834c  brfalse.s loc_8376
0x834e  ldarg.0
0x834f  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.EventViewer.SnapIn.FormControlBase::actions
0x8354  ldarg.1
0x8355  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x835a  box      [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers
0x835f  ldloc.0
0x8360  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x8365  ldarg.1
0x8366  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x836b  ldc.i4.2
0x836c  beq.s    loc_8376
0x836e  ldloc.3
0x836f  ldloc.0
0x8370  callvirt instance int32 [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItemCollection::Add(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem)
0x8375  pop
0x8376  ret
```
