# Microsoft.EventViewer.SnapIn.FormControlBase::SubScribeFromSelectEvent

- ea: `0x7ec0`
- end: `0x7fa3`
- name: `Microsoft.EventViewer.SnapIn.FormControlBase::SubScribeFromSelectEvent`
- size: `227`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x7d50`
- `0x7e80`
- `0x7ea0`

## callees

- `0x2b0`
- `0x2e0`
- `0x7ec0`

## pseudocode

```c

```

## disassembly

```asm
0x7ec0  ldarg.0
0x7ec1  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x7ec6  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x7ecb  isinst   Microsoft.EventViewer.SnapIn.ViewerRootNode
0x7ed0  stloc.0
0x7ed1  ldloc.0
0x7ed2  brfalse.s loc_7EE6
0x7ed4  ldarg.1
0x7ed5  brfalse.s loc_7EE6
0x7ed7  ldloc.0
0x7ed8  dup
0x7ed9  callvirt instance valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_EnabledStandardVerbs()
0x7ede  ldc.i4.s 0x40
0x7ee0  or
0x7ee1  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::set_EnabledStandardVerbs(valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs)
0x7ee6  ldarg.0
0x7ee7  ldfld    bool Microsoft.EventViewer.SnapIn.FormControlBase::activeView
0x7eec  ldarg.1
0x7eed  pop
0x7eee  pop
0x7eef  ldarg.0
0x7ef0  ldfld    bool Microsoft.EventViewer.SnapIn.FormControlBase::activeView
0x7ef5  ldarg.1
0x7ef6  ldc.i4.0
0x7ef7  ceq
0x7ef9  bne.un   loc_7FA2
0x7efe  ldarg.0
0x7eff  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x7f04  brfalse  loc_7FA2
0x7f09  ldarg.0
0x7f0a  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x7f0f  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SnapIn()
0x7f14  isinst   Microsoft.EventViewer.SnapIn.EventViewerSnapIn
0x7f19  stloc.1
0x7f1a  ldloc.1
0x7f1b  brfalse.s loc_7F46
0x7f1d  ldarg.1
0x7f1e  brfalse.s loc_7F33
0x7f20  ldloc.1
0x7f21  ldarg.0
0x7f22  ldftn    instance void Microsoft.EventViewer.SnapIn.FormControlBase::SelectScopeNodeHandler(object e, class [mscorlib]System.EventArgs arg)
0x7f28  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x7f2d  callvirt instance void Microsoft.EventViewer.SnapIn.EventViewerSnapIn::add_SelectScopeNode(class [mscorlib]System.EventHandler value)
0x7f32  ret
0x7f33  ldloc.1
0x7f34  ldarg.0
0x7f35  ldftn    instance void Microsoft.EventViewer.SnapIn.FormControlBase::SelectScopeNodeHandler(object e, class [mscorlib]System.EventArgs arg)
0x7f3b  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x7f40  callvirt instance void Microsoft.EventViewer.SnapIn.EventViewerSnapIn::remove_SelectScopeNode(class [mscorlib]System.EventHandler value)
0x7f45  ret
0x7f46  ldarg.0
0x7f47  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x7f4c  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SnapIn()
0x7f51  isinst   Microsoft.EventViewer.SnapIn.EventViewerExtension
0x7f56  stloc.2
0x7f57  ldloc.2
0x7f58  brfalse.s loc_7FA2
0x7f5a  ldarg.1
0x7f5b  brfalse.s loc_7F80
0x7f5d  ldloc.2
0x7f5e  dup
0x7f5f  ldfld    class [mscorlib]System.EventHandler Microsoft.EventViewer.SnapIn.EventViewerExtension::SelectScopeNode
0x7f64  ldarg.0
0x7f65  ldftn    instance void Microsoft.EventViewer.SnapIn.FormControlBase::SelectScopeNodeHandler(object e, class [mscorlib]System.EventArgs arg)
0x7f6b  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x7f70  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x7f75  castclass [mscorlib]System.EventHandler
0x7f7a  stfld    class [mscorlib]System.EventHandler Microsoft.EventViewer.SnapIn.EventViewerExtension::SelectScopeNode
0x7f7f  ret
0x7f80  ldloc.2
0x7f81  dup
0x7f82  ldfld    class [mscorlib]System.EventHandler Microsoft.EventViewer.SnapIn.EventViewerExtension::SelectScopeNode
0x7f87  ldarg.0
0x7f88  ldftn    instance void Microsoft.EventViewer.SnapIn.FormControlBase::SelectScopeNodeHandler(object e, class [mscorlib]System.EventArgs arg)
0x7f8e  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x7f93  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x7f98  castclass [mscorlib]System.EventHandler
0x7f9d  stfld    class [mscorlib]System.EventHandler Microsoft.EventViewer.SnapIn.EventViewerExtension::SelectScopeNode
0x7fa2  ret
```
