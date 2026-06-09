# PasswordRecoveryDesignerActionList::GetSortedActionItems

- ea: `0xfcb20`
- end: `0xfcbf9`
- name: `PasswordRecoveryDesignerActionList::GetSortedActionItems`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x2660`
- `0x32a20`
- `0x593e0`
- `0x598e0`
- `0x5af90`
- `0x5d870`
- `0x5d8b0`
- `0x8ef40`
- `0xfcb20`

## string_xrefs

- `0xfcba6`: `WebControls_ConvertToTemplate`
- `0xfcba1`: `ConvertToTemplate`
- `0xfcbb5`: `WebControls_ConvertToTemplateDescriptionViews`

## pseudocode

```c

```

## disassembly

```asm
0xfcb20  newobj   instance void System.ComponentModel.Design.DesignerActionItemCollection::.ctor()
0xfcb25  stloc.0
0xfcb26  ldloc.0
0xfcb27  ldstr    aView// "View"
0xfcb2c  ldstr    aWebcontrolsVie// "WebControls_Views"
0xfcb31  call     string System.Design.SR::GetString(string name)
0xfcb36  ldsfld   string [mscorlib]System.String::Empty
0xfcb3b  ldstr    aWebcontrolsVie_0// "WebControls_ViewsDescription"
0xfcb40  call     string System.Design.SR::GetString(string name)
0xfcb45  newobj   instance void System.ComponentModel.Design.DesignerActionPropertyItem::.ctor(string memberName, string displayName, string category, string description)
0xfcb4a  dup
0xfcb4b  ldc.i4.0
0xfcb4c  callvirt instance void System.ComponentModel.Design.DesignerActionItem::set_ShowInSourceView(bool value)
0xfcb51  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xfcb56  pop
0xfcb57  ldarg.0
0xfcb58  ldfld    class System.Web.UI.Design.WebControls.PasswordRecoveryDesigner PasswordRecoveryDesignerActionList::_designer
0xfcb5d  callvirt instance bool System.Web.UI.Design.ControlDesigner::get_InTemplateMode()
0xfcb62  brtrue.s loc_FCBCB
0xfcb64  ldarg.0
0xfcb65  ldfld    class System.Web.UI.Design.WebControls.PasswordRecoveryDesigner PasswordRecoveryDesignerActionList::_designer
0xfcb6a  callvirt instance bool System.Web.UI.Design.WebControls.PasswordRecoveryDesigner::get_Templated()
0xfcb6f  brfalse.s loc_FCB9F
0xfcb71  ldloc.0
0xfcb72  ldarg.0
0xfcb73  ldstr    aReset// "Reset"
0xfcb78  ldstr    aWebcontrolsRes// "WebControls_Reset"
0xfcb7d  call     string System.Design.SR::GetString(string name)
0xfcb82  ldsfld   string [mscorlib]System.String::Empty
0xfcb87  ldstr    aWebcontrolsRes_0// "WebControls_ResetDescriptionViews"
0xfcb8c  call     string System.Design.SR::GetString(string name)
0xfcb91  ldc.i4.1
0xfcb92  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xfcb97  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xfcb9c  pop
0xfcb9d  br.s     loc_FCBCB
0xfcb9f  ldloc.0
0xfcba0  ldarg.0
0xfcba1  ldstr    aConverttotempl// "ConvertToTemplate"
0xfcba6  ldstr    aWebcontrolsCon// "WebControls_ConvertToTemplate"
0xfcbab  call     string System.Design.SR::GetString(string name)
0xfcbb0  ldsfld   string [mscorlib]System.String::Empty
0xfcbb5  ldstr    aWebcontrolsCon_0// "WebControls_ConvertToTemplateDescriptio"...
0xfcbba  call     string System.Design.SR::GetString(string name)
0xfcbbf  ldc.i4.1
0xfcbc0  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xfcbc5  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xfcbca  pop
0xfcbcb  ldloc.0
0xfcbcc  ldarg.0
0xfcbcd  ldstr    aLaunchwebadmin// "LaunchWebAdmin"
0xfcbd2  ldstr    aLoginLaunchweb// "Login_LaunchWebAdmin"
0xfcbd7  call     string System.Design.SR::GetString(string name)
0xfcbdc  ldsfld   string [mscorlib]System.String::Empty
0xfcbe1  ldstr    aLoginLaunchweb_0// "Login_LaunchWebAdminDescription"
0xfcbe6  call     string System.Design.SR::GetString(string name)
0xfcbeb  ldc.i4.1
0xfcbec  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xfcbf1  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xfcbf6  pop
0xfcbf7  ldloc.0
0xfcbf8  ret
```
