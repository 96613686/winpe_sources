# Microsoft.EventViewer.SnapIn.MessageViewEx::SubScribeFromSelectEvent

- ea: `0x93d0`
- end: `0x94c5`
- name: `Microsoft.EventViewer.SnapIn.MessageViewEx::SubScribeFromSelectEvent`
- size: `245`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x9300`
- `0x9350`
- `0x93a0`

## callees

- `0x2b0`
- `0x2e0`
- `0x17c0`
- `0x17f0`
- `0x93d0`
- `0xaa90`

## pseudocode

```c

```

## disassembly

```asm
0x93d0  ldarg.0
0x93d1  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x93d6  isinst   Microsoft.EventViewer.SnapIn.ViewerRootNode
0x93db  stloc.0
0x93dc  ldloc.0
0x93dd  brfalse.s loc_9426
0x93df  ldarg.1
0x93e0  brfalse.s loc_9405
0x93e2  ldloc.0
0x93e3  dup
0x93e4  callvirt instance valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_EnabledStandardVerbs()
0x93e9  ldc.i4.s 0x40
0x93eb  or
0x93ec  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::set_EnabledStandardVerbs(valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs)
0x93f1  ldloc.0
0x93f2  ldarg.0
0x93f3  ldftn    instance void Microsoft.EventViewer.SnapIn.MessageViewEx::ScopeNodeChanged(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x93f9  newobj   instance void ViewerScopeNodeChanged::.ctor(object object, native int method)
0x93fe  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::add_ScopeNodeChanged(class ViewerScopeNodeChanged value)
0x9403  br.s     loc_9426
0x9405  ldloc.0
0x9406  dup
0x9407  callvirt instance valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_EnabledStandardVerbs()
0x940c  ldc.i4.s 0xBF
0x940e  and
0x940f  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::set_EnabledStandardVerbs(valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs)
0x9414  ldloc.0
0x9415  ldarg.0
0x9416  ldftn    instance void Microsoft.EventViewer.SnapIn.MessageViewEx::ScopeNodeChanged(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x941c  newobj   instance void ViewerScopeNodeChanged::.ctor(object object, native int method)
0x9421  callvirt instance void Microsoft.EventViewer.SnapIn.ViewerRootNode::remove_ScopeNodeChanged(class ViewerScopeNodeChanged value)
0x9426  ldarg.0
0x9427  ldfld    bool Microsoft.EventViewer.SnapIn.MessageViewEx::activeView
0x942c  ldarg.1
0x942d  ldc.i4.0
0x942e  ceq
0x9430  bne.un   loc_94C4
0x9435  ldarg.0
0x9436  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SnapIn()
0x943b  isinst   Microsoft.EventViewer.SnapIn.EventViewerSnapIn
0x9440  stloc.1
0x9441  ldloc.1
0x9442  brfalse.s loc_946D
0x9444  ldarg.1
0x9445  brfalse.s loc_945A
0x9447  ldloc.1
0x9448  ldarg.0
0x9449  ldftn    instance void Microsoft.EventViewer.SnapIn.MessageViewEx::SelectScopeNodeHandler(object e, class [mscorlib]System.EventArgs arg)
0x944f  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x9454  callvirt instance void Microsoft.EventViewer.SnapIn.EventViewerSnapIn::add_SelectScopeNode(class [mscorlib]System.EventHandler value)
0x9459  ret
0x945a  ldloc.1
0x945b  ldarg.0
0x945c  ldftn    instance void Microsoft.EventViewer.SnapIn.MessageViewEx::SelectScopeNodeHandler(object e, class [mscorlib]System.EventArgs arg)
0x9462  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x9467  callvirt instance void Microsoft.EventViewer.SnapIn.EventViewerSnapIn::remove_SelectScopeNode(class [mscorlib]System.EventHandler value)
0x946c  ret
0x946d  ldarg.0
0x946e  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SnapIn()
0x9473  isinst   Microsoft.EventViewer.SnapIn.EventViewerExtension
0x9478  stloc.2
0x9479  ldloc.2
0x947a  brfalse.s loc_94C4
0x947c  ldarg.1
0x947d  brfalse.s loc_94A2
0x947f  ldloc.2
0x9480  dup
0x9481  ldfld    class [mscorlib]System.EventHandler Microsoft.EventViewer.SnapIn.EventViewerExtension::SelectScopeNode
0x9486  ldarg.0
0x9487  ldftn    instance void Microsoft.EventViewer.SnapIn.MessageViewEx::SelectScopeNodeHandler(object e, class [mscorlib]System.EventArgs arg)
0x948d  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x9492  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x9497  castclass [mscorlib]System.EventHandler
0x949c  stfld    class [mscorlib]System.EventHandler Microsoft.EventViewer.SnapIn.EventViewerExtension::SelectScopeNode
0x94a1  ret
0x94a2  ldloc.2
0x94a3  dup
0x94a4  ldfld    class [mscorlib]System.EventHandler Microsoft.EventViewer.SnapIn.EventViewerExtension::SelectScopeNode
0x94a9  ldarg.0
0x94aa  ldftn    instance void Microsoft.EventViewer.SnapIn.MessageViewEx::SelectScopeNodeHandler(object e, class [mscorlib]System.EventArgs arg)
0x94b0  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x94b5  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x94ba  castclass [mscorlib]System.EventHandler
0x94bf  stfld    class [mscorlib]System.EventHandler Microsoft.EventViewer.SnapIn.EventViewerExtension::SelectScopeNode
0x94c4  ret
```
