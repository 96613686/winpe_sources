# Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::EditTriggerDialog

- ea: `0x79290`
- end: `0x79386`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::EditTriggerDialog`
- size: `246`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x78f40`
- `0x795f0`
- `0x79610`
- `0x79630`

## callees

- `0x12ed0`
- `0x13440`
- `0x60880`
- `0x6bac0`
- `0x6bcc0`
- `0x79290`
- `0x79a50`
- `0xa2ed0`

## string_xrefs

- `0x792ec`: `ApplicationTaskScheduler`
- `0x79336`: `ApplicationTaskScheduler`
- `0x79296`: `TitleCreateTrigger`

## pseudocode

```c

```

## disassembly

```asm
0x79290  ldnull
0x79291  stloc.0
0x79292  ldarg.1
0x79293  brtrue.s loc_792BF
0x79295  ldnull
0x79296  ldstr    aTitlecreatetri// "TitleCreateTrigger"
0x7929b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x792a0  ldc.i4.0
0x792a1  ldarg.0
0x792a2  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::GetAndDisplayTrigger(class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger trigger, valuetype UserChoice userChoice)
0x792a8  newobj   instance void DisplayTriggerDelegate::.ctor(object object, native int method)
0x792ad  ldarg.0
0x792ae  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x792b3  ldnull
0x792b4  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::.ctor(class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger inuiTriggerCurrentTrigger, string title, valuetype UserChoice userAction, class DisplayTriggerDelegate triggerDelegate, class Microsoft.Windows.ManagementUI.CombinedControls.UITask currentTask, class Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException eVal)
0x792b9  stloc.0
0x792ba  br       loc_79345
0x792bf  ldarg.0
0x792c0  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::mainListView
0x792c5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/SelectedListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_SelectedItems()
0x792ca  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListView/SelectedListViewItemCollection::get_Count()
0x792cf  ldc.i4.0
0x792d0  ble.s    loc_7932B
0x792d2  ldc.i4.s 0xC
0x792d4  ldarg.0
0x792d5  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::uiTriggerCurrentTrigger
0x792da  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskTriggerType Microsoft.Windows.ManagementUI.CombinedControls.UITrigger::get_TriggerType()
0x792df  bne.un.s loc_792FF
0x792e1  ldarg.0
0x792e2  ldstr    aMessagenomodif// "MessageNoModifyInternalTriggers"
0x792e7  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x792ec  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x792f1  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x792f6  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x792fb  ldnull
0x792fc  stloc.0
0x792fd  br.s     loc_79345
0x792ff  ldarg.0
0x79300  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::uiTriggerCurrentTrigger
0x79305  ldstr    aTitlemodifytri// "TitleModifyTrigger"
0x7930a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7930f  ldc.i4.1
0x79310  ldarg.0
0x79311  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::GetAndDisplayTrigger(class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger trigger, valuetype UserChoice userChoice)
0x79317  newobj   instance void DisplayTriggerDelegate::.ctor(object object, native int method)
0x7931c  ldarg.0
0x7931d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x79322  ldarg.2
0x79323  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::.ctor(class Microsoft.Windows.ManagementUI.CombinedControls.UITrigger inuiTriggerCurrentTrigger, string title, valuetype UserChoice userAction, class DisplayTriggerDelegate triggerDelegate, class Microsoft.Windows.ManagementUI.CombinedControls.UITask currentTask, class Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException eVal)
0x79328  stloc.0
0x79329  br.s     loc_79345
0x7932b  ldarg.0
0x7932c  ldstr    aSelectactionme// "SelectActionMessage"
0x79331  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79336  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x7933b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x79340  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x79345  ldloc.0
0x79346  brfalse.s loc_79367
0x79348  ldarg.0
0x79349  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::get_ParentEditTaskDialog()
0x7934e  ldloc.0
0x7934f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::set_ActiveChildDialog(class [System.Windows.Forms]System.Windows.Forms.Control value)
0x79354  ldloc.0
0x79355  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [System.Windows.Forms]System.Windows.Forms.Form::ShowDialog()
0x7935a  pop
0x7935b  ldarg.0
0x7935c  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::get_ParentEditTaskDialog()
0x79361  ldnull
0x79362  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::set_ActiveChildDialog(class [System.Windows.Forms]System.Windows.Forms.Control value)
0x79367  ldarg.0
0x79368  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::mainListView
0x7936d  ldarg.0
0x7936e  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.ControlTriggerList::mainListView
0x79373  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Items()
0x79378  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection::get_Count()
0x7937d  ldc.i4.0
0x7937e  cgt
0x79380  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabStop(bool)
0x79385  ret
```
