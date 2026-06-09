# Microsoft.EventViewer.SnapIn.EventViewerHomepage::SubScribeFromSelectEvent

- ea: `0x6c40`
- end: `0x6d11`
- name: `Microsoft.EventViewer.SnapIn.EventViewerHomepage::SubScribeFromSelectEvent`
- size: `209`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x6960`
- `0x6b30`
- `0x6b70`

## callees

- `0x2b0`
- `0x2e0`
- `0x6c40`

## pseudocode

```c

```

## disassembly

```asm
0x6c40  ldarg.0
0x6c41  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x6c46  isinst   Microsoft.EventViewer.SnapIn.ViewerRootNode
0x6c4b  stloc.0
0x6c4c  ldloc.0
0x6c4d  brfalse.s loc_6C72
0x6c4f  ldarg.1
0x6c50  brfalse.s loc_6C63
0x6c52  ldloc.0
0x6c53  dup
0x6c54  callvirt instance valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_EnabledStandardVerbs()
0x6c59  ldc.i4.s 0x40
0x6c5b  or
0x6c5c  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::set_EnabledStandardVerbs(valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs)
0x6c61  br.s     loc_6C72
0x6c63  ldloc.0
0x6c64  dup
0x6c65  callvirt instance valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_EnabledStandardVerbs()
0x6c6a  ldc.i4.s 0xBF
0x6c6c  and
0x6c6d  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::set_EnabledStandardVerbs(valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs)
0x6c72  ldarg.0
0x6c73  ldfld    bool Microsoft.EventViewer.SnapIn.EventViewerHomepage::activeView
0x6c78  ldarg.1
0x6c79  ldc.i4.0
0x6c7a  ceq
0x6c7c  bne.un   loc_6D10
0x6c81  ldarg.0
0x6c82  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SnapIn()
0x6c87  isinst   Microsoft.EventViewer.SnapIn.EventViewerSnapIn
0x6c8c  stloc.1
0x6c8d  ldloc.1
0x6c8e  brfalse.s loc_6CB9
0x6c90  ldarg.1
0x6c91  brfalse.s loc_6CA6
0x6c93  ldloc.1
0x6c94  ldarg.0
0x6c95  ldftn    instance void Microsoft.EventViewer.SnapIn.EventViewerHomepage::SelectScopeNodeHandler(object e, class [mscorlib]System.EventArgs arg)
0x6c9b  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6ca0  callvirt instance void Microsoft.EventViewer.SnapIn.EventViewerSnapIn::add_SelectScopeNode(class [mscorlib]System.EventHandler value)
0x6ca5  ret
0x6ca6  ldloc.1
0x6ca7  ldarg.0
0x6ca8  ldftn    instance void Microsoft.EventViewer.SnapIn.EventViewerHomepage::SelectScopeNodeHandler(object e, class [mscorlib]System.EventArgs arg)
0x6cae  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6cb3  callvirt instance void Microsoft.EventViewer.SnapIn.EventViewerSnapIn::remove_SelectScopeNode(class [mscorlib]System.EventHandler value)
0x6cb8  ret
0x6cb9  ldarg.0
0x6cba  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SnapIn()
0x6cbf  isinst   Microsoft.EventViewer.SnapIn.EventViewerExtension
0x6cc4  stloc.2
0x6cc5  ldloc.2
0x6cc6  brfalse.s loc_6D10
0x6cc8  ldarg.1
0x6cc9  brfalse.s loc_6CEE
0x6ccb  ldloc.2
0x6ccc  dup
0x6ccd  ldfld    class [mscorlib]System.EventHandler Microsoft.EventViewer.SnapIn.EventViewerExtension::SelectScopeNode
0x6cd2  ldarg.0
0x6cd3  ldftn    instance void Microsoft.EventViewer.SnapIn.EventViewerHomepage::SelectScopeNodeHandler(object e, class [mscorlib]System.EventArgs arg)
0x6cd9  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6cde  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x6ce3  castclass [mscorlib]System.EventHandler
0x6ce8  stfld    class [mscorlib]System.EventHandler Microsoft.EventViewer.SnapIn.EventViewerExtension::SelectScopeNode
0x6ced  ret
0x6cee  ldloc.2
0x6cef  dup
0x6cf0  ldfld    class [mscorlib]System.EventHandler Microsoft.EventViewer.SnapIn.EventViewerExtension::SelectScopeNode
0x6cf5  ldarg.0
0x6cf6  ldftn    instance void Microsoft.EventViewer.SnapIn.EventViewerHomepage::SelectScopeNodeHandler(object e, class [mscorlib]System.EventArgs arg)
0x6cfc  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6d01  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x6d06  castclass [mscorlib]System.EventHandler
0x6d0b  stfld    class [mscorlib]System.EventHandler Microsoft.EventViewer.SnapIn.EventViewerExtension::SelectScopeNode
0x6d10  ret
```
