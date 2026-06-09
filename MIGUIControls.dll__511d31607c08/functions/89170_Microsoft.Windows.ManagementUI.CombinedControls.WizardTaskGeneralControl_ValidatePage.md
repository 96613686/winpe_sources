# Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskGeneralControl::ValidatePage

- ea: `0x89170`
- end: `0x89272`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskGeneralControl::ValidatePage`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0x133f0`
- `0x13660`
- `0x63b20`
- `0x642b0`
- `0x645c0`
- `0x645d0`
- `0x64620`
- `0x64630`
- `0x67010`
- `0x867e0`
- `0x86820`
- `0x86830`
- `0x874d0`
- `0x874e0`
- `0x89170`

## string_xrefs

- `0x89261`: `Please enter a task name.`

## pseudocode

```c

```

## disassembly

```asm
0x89170  ldarg.0
0x89171  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl::get_WizardManager()
0x89176  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::get_CurrentTask()
0x8917b  ldarg.0
0x8917c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskGeneralControl::textBoxName
0x89181  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::GetControlText(class [System.Windows.Forms]System.Windows.Forms.Control ctl)
0x89186  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITask::set_Name(string value)
0x8918b  ldarg.0
0x8918c  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl::get_WizardManager()
0x89191  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::get_CurrentFolder()
0x89196  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::get_Path()
0x8919b  ldstr    asc_A80EC// "\\"
0x891a0  ldc.i4.4
0x891a1  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x891a6  brfalse.s loc_891DF
0x891a8  ldarg.0
0x891a9  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl::get_WizardManager()
0x891ae  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::get_CurrentTask()
0x891b3  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_PreviewInfo()
0x891b8  ldarg.0
0x891b9  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl::get_WizardManager()
0x891be  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::get_CurrentFolder()
0x891c3  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::get_Path()
0x891c8  ldarg.0
0x891c9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskGeneralControl::textBoxName
0x891ce  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x891d3  call     string [mscorlib]System.String::Concat(string, string)
0x891d8  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo::set_Path(string value)
0x891dd  br.s     loc_89221
0x891df  ldarg.0
0x891e0  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl::get_WizardManager()
0x891e5  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::get_CurrentTask()
0x891ea  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_PreviewInfo()
0x891ef  ldarg.0
0x891f0  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl::get_WizardManager()
0x891f5  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::get_CurrentFolder()
0x891fa  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::get_Path()
0x891ff  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x89204  stloc.0
0x89205  ldloca.s 0
0x89207  call     instance string [mscorlib]System.Char::ToString()
0x8920c  ldarg.0
0x8920d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskGeneralControl::textBoxName
0x89212  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x89217  call     string [mscorlib]System.String::Concat(string, string, string)
0x8921c  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo::set_Path(string value)
0x89221  ldarg.0
0x89222  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl::get_WizardManager()
0x89227  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::get_CurrentTask()
0x8922c  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x89231  ldarg.0
0x89232  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskGeneralControl::textBoxDescription
0x89237  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::GetControlText(class [System.Windows.Forms]System.Windows.Forms.Control ctl)
0x8923c  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::set_Description(string value)
0x89241  ldarg.0
0x89242  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl::get_WizardManager()
0x89247  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::get_CurrentTask()
0x8924c  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x89251  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x89256  brtrue.s loc_89261
0x89258  ldarg.0
0x89259  ldc.i4.1
0x8925a  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl::set_PageReady(bool value)
0x8925f  br.s     loc_8926B
0x89261  ldstr    aPleaseEnterATa// "Please enter a task name."
0x89266  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x8926b  ldarg.0
0x8926c  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.WizardBaseControl::get_PageReady()
0x89271  ret
```
