# Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::EditActionDialog

- ea: `0x68ff0`
- end: `0x690f8`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::EditActionDialog`
- size: `264`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x69280`
- `0x69290`
- `0x69340`

## callees

- `0x12ed0`
- `0x13440`
- `0x5f840`
- `0x68ff0`
- `0x69a70`
- `0x69a90`
- `0x6bac0`
- `0x6bcc0`
- `0xa2f20`

## string_xrefs

- `0x690a7`: `ApplicationTaskScheduler`
- `0x690c5`: `ApplicationTaskScheduler`
- `0x68ffd`: `TitleCreateAction`

## pseudocode

```c

```

## disassembly

```asm
0x68ff0  ldnull
0x68ff1  stloc.0
0x68ff2  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::.ctor()
0x68ff7  stloc.0
0x68ff8  ldarg.1
0x68ff9  brtrue.s loc_69024
0x68ffb  ldloc.0
0x68ffc  ldnull
0x68ffd  ldstr    aTitlecreateact// "TitleCreateAction"
0x69002  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x69007  ldc.i4.0
0x69008  ldarg.0
0x69009  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::GetAndDisplayAction(class Microsoft.Windows.ManagementUI.CombinedControls.UIAction action, valuetype UserChoice userChoice)
0x6900f  newobj   instance void DisplayActionDelegate::.ctor(object object, native int method)
0x69014  ldarg.0
0x69015  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::taskVersion
0x6901a  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::Initialize(class Microsoft.Windows.ManagementUI.CombinedControls.UIAction inAction, string title, valuetype UserChoice userActionChoice, class DisplayActionDelegate actionDelegate, valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility inTaskVersion)
0x6901f  br       loc_690D4
0x69024  ldarg.0
0x69025  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::listViewActions
0x6902a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/SelectedListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_SelectedItems()
0x6902f  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListView/SelectedListViewItemCollection::get_Count()
0x69034  ldc.i4.0
0x69035  ble      loc_690BA
0x6903a  ldarg.0
0x6903b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::uiCurrentAction
0x69040  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskActionType Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_ActionType()
0x69045  brfalse.s loc_69063
0x69047  ldc.i4.6
0x69048  ldarg.0
0x69049  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::uiCurrentAction
0x6904e  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskActionType Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_ActionType()
0x69053  beq.s    loc_69063
0x69055  ldc.i4.7
0x69056  ldarg.0
0x69057  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::uiCurrentAction
0x6905c  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskActionType Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_ActionType()
0x69061  bne.un.s loc_6908E
0x69063  ldloc.0
0x69064  ldarg.0
0x69065  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::uiCurrentAction
0x6906a  ldstr    aTitlemodifyact// "TitleModifyAction"
0x6906f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x69074  ldc.i4.1
0x69075  ldarg.0
0x69076  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::GetAndDisplayAction(class Microsoft.Windows.ManagementUI.CombinedControls.UIAction action, valuetype UserChoice userChoice)
0x6907c  newobj   instance void DisplayActionDelegate::.ctor(object object, native int method)
0x69081  ldarg.0
0x69082  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::taskVersion
0x69087  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::Initialize(class Microsoft.Windows.ManagementUI.CombinedControls.UIAction inAction, string title, valuetype UserChoice userActionChoice, class DisplayActionDelegate actionDelegate, valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility inTaskVersion)
0x6908c  br.s     loc_690D4
0x6908e  ldc.i4.5
0x6908f  ldarg.0
0x69090  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UIAction Microsoft.Windows.ManagementUI.CombinedControls.ControlActionList::uiCurrentAction
0x69095  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskActionType Microsoft.Windows.ManagementUI.CombinedControls.UIAction::get_ActionType()
0x6909a  bne.un.s loc_690D4
0x6909c  ldarg.0
0x6909d  ldstr    aMessagenomodif_0// "MessageNoModifyCustomHandlers"
0x690a2  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x690a7  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x690ac  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x690b1  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x690b6  ldnull
0x690b7  stloc.0
0x690b8  br.s     loc_690D4
0x690ba  ldarg.0
0x690bb  ldstr    aSelectactionme// "SelectActionMessage"
0x690c0  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x690c5  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x690ca  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x690cf  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x690d4  ldloc.0
0x690d5  brfalse.s loc_690F7
0x690d7  ldarg.0
0x690d8  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::get_ParentEditTaskDialog()
0x690dd  ldloc.0
0x690de  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::set_ActiveChildDialog(class [System.Windows.Forms]System.Windows.Forms.Control value)
0x690e3  ldloc.0
0x690e4  ldarg.0
0x690e5  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [System.Windows.Forms]System.Windows.Forms.Form::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.IWin32Window)
0x690ea  pop
0x690eb  ldarg.0
0x690ec  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::get_ParentEditTaskDialog()
0x690f1  ldnull
0x690f2  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::set_ActiveChildDialog(class [System.Windows.Forms]System.Windows.Forms.Control value)
0x690f7  ret
```
