# Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::Next

- ea: `0x87dd0`
- end: `0x87fe8`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::Next`
- size: `536`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x880b0`
- `0x880d0`

## callees

- `0x12ed0`
- `0x5d740`
- `0x5d760`
- `0x645c0`
- `0x67bb0`
- `0x6bd00`
- `0x6bd20`
- `0x86870`
- `0x86880`
- `0x874d0`
- `0x87d10`
- `0x87dd0`
- `0x88070`
- `0x889f0`
- `0x88aa0`

## string_xrefs

- `0x87e4f`: `LocalComputer`
- `0x87e73`: `TitleModifyTask`

## pseudocode

```c

```

## disassembly

```asm
0x87dd0  ldarg.0
0x87dd1  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberPages
0x87dd6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x87ddb  ldc.i4.1
0x87ddc  sub
0x87ddd  ldarg.0
0x87dde  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberCurrentPageIndex
0x87de3  bne.un   loc_87EF7
0x87de8  ldnull
0x87de9  stloc.0
0x87dea  ldarg.0
0x87deb  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::SubmitTask()
0x87df0  brfalse  loc_87EDB
0x87df5  ldarg.0
0x87df6  ldc.i4.1
0x87df7  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x87dfc  ldarg.0
0x87dfd  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberPages
0x87e02  ldarg.0
0x87e03  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberPages
0x87e08  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x87e0d  ldc.i4.1
0x87e0e  sub
0x87e0f  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x87e14  castclass Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl
0x87e19  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::get_OpenPropertiesDialog()
0x87e1e  brfalse  loc_87EDB
0x87e23  ldarg.0
0x87e24  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::uiTaskCurrentTask
0x87e29  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x87e2e  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_ComputerName()
0x87e33  stloc.1
0x87e34  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::.ctor()
0x87e39  stloc.0
0x87e3a  ldloc.1
0x87e3b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x87e40  brtrue.s loc_87E4F
0x87e42  ldstr    asc_A98C0// "."
0x87e47  ldloc.1
0x87e48  call     instance bool [mscorlib]System.String::Equals(string)
0x87e4d  brfalse.s loc_87E5A
0x87e4f  ldstr    aLocalcomputer// "LocalComputer"
0x87e54  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x87e59  stloc.1
0x87e5a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x87e5f  ldtoken  [mscorlib]System.String
0x87e64  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x87e69  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x87e6e  castclass [mscorlib]System.IFormatProvider
0x87e73  ldstr    aTitlemodifytas// "TitleModifyTask"
0x87e78  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x87e7d  ldc.i4.2
0x87e7e  newarr   [mscorlib]System.Object
0x87e83  dup
0x87e84  ldc.i4.0
0x87e85  ldarg.0
0x87e86  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::get_CurrentTask()
0x87e8b  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x87e90  stelem.ref
0x87e91  dup
0x87e92  ldc.i4.1
0x87e93  ldloc.1
0x87e94  stelem.ref
0x87e95  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x87e9a  stloc.2
0x87e9b  ldloc.0
0x87e9c  ldarg.0
0x87e9d  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::get_CurrentTask()
0x87ea2  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_Parent()
0x87ea7  castclass Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder
0x87eac  ldarg.0
0x87ead  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::get_CurrentTask()
0x87eb2  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x87eb7  ldloc.2
0x87eb8  ldc.i4.1
0x87eb9  ldarg.0
0x87eba  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::ownerTaskSchedulerView
0x87ebf  ldnull
0x87ec0  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::Initialize(class Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder folder, string taskName, string title, valuetype UserChoice userAction, class Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl inOwnerView, string inXmlText)
0x87ec5  brfalse.s loc_87ED5
0x87ec7  ldarg.0
0x87ec8  ldc.i4.0
0x87ec9  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x87ece  ldloc.0
0x87ecf  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [System.Windows.Forms]System.Windows.Forms.Form::ShowDialog()
0x87ed4  pop
0x87ed5  ldloc.0
0x87ed6  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0x87edb  leave    loc_87FE1
0x87ee0  pop
0x87ee1  ldarg.0
0x87ee2  ldc.i4.2
0x87ee3  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x87ee8  leave    loc_87FE1
0x87eed  ldloc.0
0x87eee  brfalse.s loc_87EF6
0x87ef0  ldloc.0
0x87ef1  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0x87ef6  endfinally
0x87ef7  ldarg.0
0x87ef8  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberCurrentPageIndex
0x87efd  ldarg.0
0x87efe  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberPages
0x87f03  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x87f08  ldc.i4.1
0x87f09  sub
0x87f0a  bge      loc_87FE1
0x87f0f  ldarg.0
0x87f10  ldc.i4.0
0x87f11  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x87f16  ldarg.0
0x87f17  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberCurrentPage
0x87f1c  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl::ValidatePage()
0x87f21  brfalse  loc_87FE1
0x87f26  ldarg.0
0x87f27  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberCurrentPage
0x87f2c  ldc.i4.0
0x87f2d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x87f32  ldarg.0
0x87f33  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberPages
0x87f38  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x87f3d  stloc.s  4
0x87f3f  br.s     loc_87F53
0x87f41  ldloc.s  4
0x87f43  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x87f48  castclass [System.Windows.Forms]System.Windows.Forms.Control
0x87f4d  ldc.i4.0
0x87f4e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x87f53  ldloc.s  4
0x87f55  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x87f5a  brtrue.s loc_87F41
0x87f5c  leave.s  loc_87F73
0x87f5e  ldloc.s  4
0x87f60  isinst   [mscorlib]System.IDisposable
0x87f65  stloc.s  5
0x87f67  ldloc.s  5
0x87f69  brfalse.s loc_87F72
0x87f6b  ldloc.s  5
0x87f6d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x87f72  endfinally
0x87f73  ldarg.0
0x87f74  ldarg.0
0x87f75  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberCurrentPageIndex
0x87f7a  ldc.i4.1
0x87f7b  add
0x87f7c  stfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberCurrentPageIndex
0x87f81  ldarg.0
0x87f82  ldarg.0
0x87f83  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberPages
0x87f88  ldarg.0
0x87f89  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberCurrentPageIndex
0x87f8e  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x87f93  castclass Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl
0x87f98  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberCurrentPage
0x87f9d  ldarg.0
0x87f9e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberCurrentPage
0x87fa3  isinst   Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl
0x87fa8  stloc.3
0x87fa9  ldloc.3
0x87faa  brfalse.s loc_87FB2
0x87fac  ldloc.3
0x87fad  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::UpdateTaskDescription()
0x87fb2  ldarg.0
0x87fb3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberCurrentPage
0x87fb8  ldc.i4.1
0x87fb9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x87fbe  ldarg.0
0x87fbf  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberCurrentPage
0x87fc4  ldc.i4.1
0x87fc5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x87fca  ldarg.0
0x87fcb  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberCurrentPage
0x87fd0  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl::ShowControl()
0x87fd5  ldarg.0
0x87fd6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberCurrentPage
0x87fdb  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::Focus()
0x87fe0  pop
0x87fe1  ldarg.0
0x87fe2  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::ToggleBackButton()
0x87fe7  ret
```
