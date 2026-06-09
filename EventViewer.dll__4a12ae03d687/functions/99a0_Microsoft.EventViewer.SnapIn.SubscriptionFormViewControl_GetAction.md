# Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::GetAction

- ea: `0x99a0`
- end: `0x9c39`
- name: `Microsoft.EventViewer.SnapIn.SubscriptionFormViewControl::GetAction`
- size: `665`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x8010`
- `0x8380`
- `0x8570`
- `0x8680`
- `0x9070`
- `0x99a0`

## string_xrefs

- `0x9a30`: `StandardDelete`
- `0x9a40`: `DeleteSubscriptionDesc`

## pseudocode

```c

```

## disassembly

```asm
0x99a0  ldnull
0x99a1  stloc.0
0x99a2  ldarg.2
0x99a3  ldnull
0x99a4  stind.ref
0x99a5  ldc.i4.0
0x99a6  stloc.1
0x99a7  ldarg.1
0x99a8  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x99ad  stloc.2
0x99ae  ldloc.2
0x99af  ldc.i4.s 0x27
0x99b1  sub
0x99b2  switch   loc_99D4, loc_9A29, loc_9B28, loc_9B7D, loc_9A7E, loc_9AD3
0x99cf  br       loc_9BCF
0x99d4  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SyncAction::.ctor()
0x99d9  stloc.0
0x99da  ldloc.0
0x99db  ldstr    aActionProperti// "ACTION_PROPERTIES"
0x99e0  call     string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string)
0x99e5  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x99ea  ldloc.0
0x99eb  ldstr    aActionProperti// "ACTION_PROPERTIES"
0x99f0  call     string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string)
0x99f5  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_Description(string)
0x99fa  ldloc.0
0x99fb  ldarg.1
0x99fc  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x9a01  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndex(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x9a06  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x9a0b  ldarg.1
0x9a0c  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x9a11  ldloca.s 0
0x9a13  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& action)
0x9a18  ldloc.0
0x9a19  ldarg.1
0x9a1a  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x9a1f  ldarg.2
0x9a20  ldloc.0
0x9a21  stind.ref
0x9a22  ldc.i4.1
0x9a23  stloc.1
0x9a24  br       loc_9C01
0x9a29  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SyncAction::.ctor()
0x9a2e  stloc.0
0x9a2f  ldloc.0
0x9a30  ldstr    aStandarddelete// "StandardDelete"
0x9a35  call     string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string)
0x9a3a  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x9a3f  ldloc.0
0x9a40  ldstr    aDeletesubscrip// "DeleteSubscriptionDesc"
0x9a45  call     string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string)
0x9a4a  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_Description(string)
0x9a4f  ldloc.0
0x9a50  ldarg.1
0x9a51  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x9a56  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndex(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x9a5b  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x9a60  ldarg.1
0x9a61  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x9a66  ldloca.s 0
0x9a68  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& action)
0x9a6d  ldloc.0
0x9a6e  ldarg.1
0x9a6f  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x9a74  ldarg.2
0x9a75  ldloc.0
0x9a76  stind.ref
0x9a77  ldc.i4.1
0x9a78  stloc.1
0x9a79  br       loc_9C01
0x9a7e  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Action::.ctor()
0x9a83  stloc.0
0x9a84  ldloc.0
0x9a85  ldstr    aRetry// "Retry"
0x9a8a  call     string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string)
0x9a8f  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x9a94  ldloc.0
0x9a95  ldstr    aRetrysubscript// "RetrySubscriptionDesc"
0x9a9a  call     string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string)
0x9a9f  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_Description(string)
0x9aa4  ldloc.0
0x9aa5  ldarg.1
0x9aa6  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x9aab  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndex(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x9ab0  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x9ab5  ldarg.1
0x9ab6  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x9abb  ldloca.s 0
0x9abd  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& action)
0x9ac2  ldloc.0
0x9ac3  ldarg.1
0x9ac4  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x9ac9  ldarg.2
0x9aca  ldloc.0
0x9acb  stind.ref
0x9acc  ldc.i4.1
0x9acd  stloc.1
0x9ace  br       loc_9C01
0x9ad3  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Action::.ctor()
0x9ad8  stloc.0
0x9ad9  ldloc.0
0x9ada  ldstr    aSubscriptionst// "SubscriptionStatus"
0x9adf  call     string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string)
0x9ae4  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x9ae9  ldloc.0
0x9aea  ldstr    aSubscriptionst_0// "SubscriptionStatusDesc"
0x9aef  call     string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string)
0x9af4  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_Description(string)
0x9af9  ldloc.0
0x9afa  ldarg.1
0x9afb  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x9b00  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndex(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x9b05  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x9b0a  ldarg.1
0x9b0b  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x9b10  ldloca.s 0
0x9b12  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& action)
0x9b17  ldloc.0
0x9b18  ldarg.1
0x9b19  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x9b1e  ldarg.2
0x9b1f  ldloc.0
0x9b20  stind.ref
0x9b21  ldc.i4.1
0x9b22  stloc.1
0x9b23  br       loc_9C01
0x9b28  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Action::.ctor()
0x9b2d  stloc.0
0x9b2e  ldloc.0
0x9b2f  ldstr    aEnable// "Enable"
0x9b34  call     string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string)
0x9b39  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x9b3e  ldloc.0
0x9b3f  ldstr    aEnablesubscrip// "EnableSubscriptionDesc"
0x9b44  call     string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string)
0x9b49  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_Description(string)
0x9b4e  ldloc.0
0x9b4f  ldarg.1
0x9b50  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x9b55  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndex(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x9b5a  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x9b5f  ldarg.1
0x9b60  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x9b65  ldloca.s 0
0x9b67  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& action)
0x9b6c  ldloc.0
0x9b6d  ldarg.1
0x9b6e  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x9b73  ldarg.2
0x9b74  ldloc.0
0x9b75  stind.ref
0x9b76  ldc.i4.1
0x9b77  stloc.1
0x9b78  br       loc_9C01
0x9b7d  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Action::.ctor()
0x9b82  stloc.0
0x9b83  ldloc.0
0x9b84  ldstr    aDisable// "Disable"
0x9b89  call     string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string)
0x9b8e  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_DisplayName(string)
0x9b93  ldloc.0
0x9b94  ldstr    aDisablesubscri// "DisableSubscriptionDesc"
0x9b99  call     string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string)
0x9b9e  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_Description(string)
0x9ba3  ldloc.0
0x9ba4  ldarg.1
0x9ba5  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x9baa  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndex(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x9baf  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x9bb4  ldarg.1
0x9bb5  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Status()
0x9bba  ldloca.s 0
0x9bbc  call     void Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementActionStatus status, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& action)
0x9bc1  ldloc.0
0x9bc2  ldarg.1
0x9bc3  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem::set_Tag(object)
0x9bc8  ldarg.2
0x9bc9  ldloc.0
0x9bca  stind.ref
0x9bcb  ldc.i4.1
0x9bcc  stloc.1
0x9bcd  br.s     loc_9C01
0x9bcf  ldstr    aThisActionForR_1// "This action for result control is not s"...
0x9bd4  ldarg.1
0x9bd5  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x9bda  stloc.3
0x9bdb  ldloca.s 3
0x9bdd  constrained. [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers
0x9be3  callvirt instance string [mscorlib]System.Object::ToString()
0x9be8  call     string [mscorlib]System.String::Concat(string, string)
0x9bed  call     void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string)
0x9bf2  newobj   instance void [mscorlib]System.Diagnostics.StackTrace::.ctor()
0x9bf7  callvirt instance string [mscorlib]System.Object::ToString()
0x9bfc  call     void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string)
0x9c01  ldloc.1
0x9c02  brfalse.s loc_9C2B
0x9c04  ldarg.2
0x9c05  ldind.ref
0x9c06  isinst   [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase
0x9c0b  stloc.0
0x9c0c  ldloc.0
0x9c0d  brfalse.s loc_9C2B
0x9c0f  ldarg.0
0x9c10  ldloca.s 0
0x9c12  call     instance void Microsoft.EventViewer.SnapIn.FormControlBase::SetTriggeredForAction(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& actBase)
0x9c17  ldloc.0
0x9c18  ldarg.1
0x9c19  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x9c1e  call     int32 Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndexForAction(valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers actionId)
0x9c23  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneExtendedItem::set_ImageIndex(int32)
0x9c28  ldarg.2
0x9c29  ldloc.0
0x9c2a  stind.ref
0x9c2b  ldloc.1
0x9c2c  brfalse.s loc_9C30
0x9c2e  ldloc.1
0x9c2f  ret
0x9c30  ldarg.0
0x9c31  ldarg.1
0x9c32  ldarg.2
0x9c33  call     instance bool Microsoft.EventViewer.SnapIn.FormControlBase::GetAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action, [out] class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem& actionOut)
0x9c38  ret
```
