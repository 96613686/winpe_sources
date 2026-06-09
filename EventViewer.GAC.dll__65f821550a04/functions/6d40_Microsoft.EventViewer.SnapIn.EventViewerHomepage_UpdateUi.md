# Microsoft.EventViewer.SnapIn.EventViewerHomepage::UpdateUi

- ea: `0x6d40`
- end: `0x6e97`
- name: `Microsoft.EventViewer.SnapIn.EventViewerHomepage::UpdateUi`
- size: `343`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x6d40`

## pseudocode

```c

```

## disassembly

```asm
0x6d40  ldarg.1
0x6d41  ldc.i4.1
0x6d42  sub
0x6d43  switch   loc_6DC3, loc_6D59, loc_6E96, loc_6E2D
0x6d58  ret
0x6d59  ldarg.0
0x6d5a  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x6d5f  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_SnapIn()
0x6d64  ldarg.0
0x6d65  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl Microsoft.EventViewer.SnapIn.EventViewerHomepage::eventHomeControl
0x6d6a  ldftn    instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::UpdateUiToShowFailure()
0x6d70  newobj   instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl/UpdateUiDelegate::.ctor(object, native int)
0x6d75  callvirt instance class [mscorlib]System.IAsyncResult [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase::BeginInvoke(class [mscorlib]System.Delegate)
0x6d7a  dup
0x6d7b  callvirt instance class [mscorlib]System.Threading.WaitHandle [mscorlib]System.IAsyncResult::get_AsyncWaitHandle()
0x6d80  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x6d85  pop
0x6d86  ldarg.0
0x6d87  ldfld    bool Microsoft.EventViewer.SnapIn.EventViewerHomepage::activeView
0x6d8c  brfalse.s loc_6DA4
0x6d8e  ldarg.0
0x6d8f  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x6d94  dup
0x6d95  callvirt instance valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_EnabledStandardVerbs()
0x6d9a  ldc.i4.s 0x40
0x6d9c  or
0x6d9d  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::set_EnabledStandardVerbs(valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs)
0x6da2  br.s     loc_6DB8
0x6da4  ldarg.0
0x6da5  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x6daa  dup
0x6dab  callvirt instance valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_EnabledStandardVerbs()
0x6db0  ldc.i4.s 0xBF
0x6db2  and
0x6db3  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::set_EnabledStandardVerbs(valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs)
0x6db8  callvirt instance class [mscorlib]System.Threading.WaitHandle [mscorlib]System.IAsyncResult::get_AsyncWaitHandle()
0x6dbd  callvirt instance void [mscorlib]System.Threading.WaitHandle::Close()
0x6dc2  ret
0x6dc3  ldarg.0
0x6dc4  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x6dc9  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_SnapIn()
0x6dce  ldarg.0
0x6dcf  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl Microsoft.EventViewer.SnapIn.EventViewerHomepage::eventHomeControl
0x6dd4  ldftn    instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::UpdateUiToShowSuccess()
0x6dda  newobj   instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl/UpdateUiDelegate::.ctor(object, native int)
0x6ddf  callvirt instance class [mscorlib]System.IAsyncResult [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase::BeginInvoke(class [mscorlib]System.Delegate)
0x6de4  dup
0x6de5  callvirt instance class [mscorlib]System.Threading.WaitHandle [mscorlib]System.IAsyncResult::get_AsyncWaitHandle()
0x6dea  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x6def  pop
0x6df0  ldarg.0
0x6df1  ldfld    bool Microsoft.EventViewer.SnapIn.EventViewerHomepage::activeView
0x6df6  brfalse.s loc_6E0E
0x6df8  ldarg.0
0x6df9  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x6dfe  dup
0x6dff  callvirt instance valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_EnabledStandardVerbs()
0x6e04  ldc.i4.s 0x40
0x6e06  or
0x6e07  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::set_EnabledStandardVerbs(valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs)
0x6e0c  br.s     loc_6E22
0x6e0e  ldarg.0
0x6e0f  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x6e14  dup
0x6e15  callvirt instance valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_EnabledStandardVerbs()
0x6e1a  ldc.i4.s 0xBF
0x6e1c  and
0x6e1d  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::set_EnabledStandardVerbs(valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs)
0x6e22  callvirt instance class [mscorlib]System.Threading.WaitHandle [mscorlib]System.IAsyncResult::get_AsyncWaitHandle()
0x6e27  callvirt instance void [mscorlib]System.Threading.WaitHandle::Close()
0x6e2c  ret
0x6e2d  ldarg.0
0x6e2e  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x6e33  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Node::get_SnapIn()
0x6e38  ldarg.0
0x6e39  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl Microsoft.EventViewer.SnapIn.EventViewerHomepage::eventHomeControl
0x6e3e  ldftn    instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::UpdateUiToShowCancelled()
0x6e44  newobj   instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl/UpdateUiDelegate::.ctor(object, native int)
0x6e49  callvirt instance class [mscorlib]System.IAsyncResult [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInBase::BeginInvoke(class [mscorlib]System.Delegate)
0x6e4e  dup
0x6e4f  callvirt instance class [mscorlib]System.Threading.WaitHandle [mscorlib]System.IAsyncResult::get_AsyncWaitHandle()
0x6e54  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x6e59  pop
0x6e5a  ldarg.0
0x6e5b  ldfld    bool Microsoft.EventViewer.SnapIn.EventViewerHomepage::activeView
0x6e60  brfalse.s loc_6E78
0x6e62  ldarg.0
0x6e63  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x6e68  dup
0x6e69  callvirt instance valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_EnabledStandardVerbs()
0x6e6e  ldc.i4.s 0x40
0x6e70  or
0x6e71  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::set_EnabledStandardVerbs(valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs)
0x6e76  br.s     loc_6E8C
0x6e78  ldarg.0
0x6e79  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_ScopeNode()
0x6e7e  dup
0x6e7f  callvirt instance valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::get_EnabledStandardVerbs()
0x6e84  ldc.i4.s 0xBF
0x6e86  and
0x6e87  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode::set_EnabledStandardVerbs(valuetype [Microsoft.ManagementConsole]Microsoft.ManagementConsole.StandardVerbs)
0x6e8c  callvirt instance class [mscorlib]System.Threading.WaitHandle [mscorlib]System.IAsyncResult::get_AsyncWaitHandle()
0x6e91  callvirt instance void [mscorlib]System.Threading.WaitHandle::Close()
0x6e96  ret
```
