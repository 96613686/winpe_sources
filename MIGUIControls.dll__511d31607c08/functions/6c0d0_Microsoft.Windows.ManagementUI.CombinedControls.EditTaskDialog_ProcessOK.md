# Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::ProcessOK

- ea: `0x6c0d0`
- end: `0x6c1ef`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::ProcessOK`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x6c1f0`

## callees

- `0x12ed0`
- `0x13440`
- `0x5d760`
- `0x645c0`
- `0x67ce0`
- `0x6c0d0`
- `0x6c3b0`
- `0x6ced0`

## string_xrefs

- `0x6c10e`: `ApplicationTaskScheduler`
- `0x6c183`: `ApplicationTaskScheduler`
- `0x6c0e8`: `MessageSpecificTaskNotFound`
- `0x6c159`: `TheLocalComputer`
- `0x6c165`: `MessageTaskEditServiceChanged`

## pseudocode

```c

```

## disassembly

```asm
0x6c0d0  ldc.i4.0
0x6c0d1  stloc.0
0x6c0d2  ldc.i4.0
0x6c0d3  stloc.1
0x6c0d4  ldarg.0
0x6c0d5  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::allowOkProcessing
0x6c0da  brfalse.s loc_6C0E4
0x6c0dc  ldarg.0
0x6c0dd  ldc.i4.1
0x6c0de  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::UpdateTask(bool reload)
0x6c0e3  stloc.0
0x6c0e4  leave.s  loc_6C13F
0x6c0e6  pop
0x6c0e7  ldnull
0x6c0e8  ldstr    aMessagespecifi// "MessageSpecificTaskNotFound"
0x6c0ed  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6c0f2  ldc.i4.1
0x6c0f3  newarr   [mscorlib]System.Object
0x6c0f8  dup
0x6c0f9  ldc.i4.0
0x6c0fa  ldarg.0
0x6c0fb  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::uiTaskCurrentTask
0x6c100  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x6c105  stelem.ref
0x6c106  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6c10b  stloc.2
0x6c10c  ldarg.0
0x6c10d  ldloc.2
0x6c10e  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x6c113  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6c118  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x6c11d  ldc.i4.1
0x6c11e  stloc.1
0x6c11f  ldarg.0
0x6c120  ldc.i4.0
0x6c121  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::allowOkProcessing
0x6c126  leave.s  loc_6C13F
0x6c128  pop
0x6c129  ldarg.0
0x6c12a  ldfld    valuetype UserChoice Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::userActionChoice
0x6c12f  ldc.i4.1
0x6c130  bne.un.s loc_6C13B
0x6c132  ldarg.0
0x6c133  ldc.i4.0
0x6c134  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::allowOkProcessing
0x6c139  br.s     loc_6C13D
0x6c13b  ldc.i4.1
0x6c13c  stloc.0
0x6c13d  leave.s  loc_6C13F
0x6c13f  ldarg.0
0x6c140  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::allowOkProcessing
0x6c145  brtrue.s loc_6C192
0x6c147  ldloc.1
0x6c148  brtrue.s loc_6C192
0x6c14a  ldarg.0
0x6c14b  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::currentSystem
0x6c150  stloc.3
0x6c151  ldloc.3
0x6c152  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6c157  brfalse.s loc_6C164
0x6c159  ldstr    aThelocalcomput// "TheLocalComputer"
0x6c15e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6c163  stloc.3
0x6c164  ldnull
0x6c165  ldstr    aMessagetaskedi// "MessageTaskEditServiceChanged"
0x6c16a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6c16f  ldc.i4.1
0x6c170  newarr   [mscorlib]System.Object
0x6c175  dup
0x6c176  ldc.i4.0
0x6c177  ldloc.3
0x6c178  stelem.ref
0x6c179  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6c17e  stloc.s  4
0x6c180  ldarg.0
0x6c181  ldloc.s  4
0x6c183  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x6c188  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6c18d  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x6c192  ldloc.0
0x6c193  brfalse.s loc_6C1E7
0x6c195  ldarg.0
0x6c196  ldfld    valuetype UserChoice Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::userActionChoice
0x6c19b  ldc.i4.1
0x6c19c  bne.un.s loc_6C1E0
0x6c19e  ldsfld   class Microsoft.Windows.ManagementUI.CombinedControls.TaskPropertyDialogManager Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::taskPropertyDialogManager
0x6c1a3  ldarg.0
0x6c1a4  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::currentSystem
0x6c1a9  ldarg.0
0x6c1aa  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::taskPath
0x6c1af  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskPropertyDialogManager::RemoveTask(string systemName, string taskPath)
0x6c1b4  ldarg.0
0x6c1b5  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::uiTaskCurrentTask
0x6c1ba  brfalse.s loc_6C1E0
0x6c1bc  ldarg.0
0x6c1bd  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::uiTaskCurrentTask
0x6c1c2  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x6c1c7  stloc.s  5
0x6c1c9  ldloc.s  5
0x6c1cb  brfalse.s loc_6C1E0
0x6c1cd  ldloc.s  5
0x6c1cf  ldarg.0
0x6c1d0  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::OnTaskServiceDataChanged(object sender, class UITaskServiceEventArgs eventArgs)
0x6c1d6  newobj   instance void class [mscorlib]System.EventHandler`1<class UITaskServiceEventArgs>::.ctor(object, native int)
0x6c1db  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::remove_DataChanged(class [mscorlib]System.EventHandler`1<class UITaskServiceEventArgs> value)
0x6c1e0  ldarg.0
0x6c1e1  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::Close()
0x6c1e6  ret
0x6c1e7  ldarg.0
0x6c1e8  ldc.i4.0
0x6c1e9  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x6c1ee  ret
```
