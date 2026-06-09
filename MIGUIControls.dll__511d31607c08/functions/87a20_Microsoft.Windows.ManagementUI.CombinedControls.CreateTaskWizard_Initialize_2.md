# Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::Initialize_2

- ea: `0x87a20`
- end: `0x87b19`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::Initialize_2`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x822c0`

## callees

- `0x12ed0`
- `0x14500`
- `0x86960`
- `0x87540`
- `0x878d0`
- `0x87a20`
- `0x87c40`
- `0x88a00`
- `0x89020`
- `0x89620`

## string_xrefs

- `0x87a3d`: `ParentWelcome`
- `0x87a4d`: `ParentWelcome`

## pseudocode

```c

```

## disassembly

```asm
0x87a20  ldarg.0
0x87a21  ldc.i4.1
0x87a22  stfld    valuetype TaskOwnerEnum Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::ownerOfTask
0x87a27  ldarg.0
0x87a28  ldarg.1
0x87a29  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::InitializeCommonData(class Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder folder)
0x87a2e  dup
0x87a2f  brfalse  loc_87B18
0x87a34  ldarg.0
0x87a35  ldarg.2
0x87a36  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::ownerTaskSchedulerView
0x87a3b  ldarg.0
0x87a3c  ldnull
0x87a3d  ldstr    aParentwelcome// "ParentWelcome"
0x87a42  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x87a47  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::AddPageSelection(string precedingPage, string pageToAdd)
0x87a4c  ldarg.0
0x87a4d  ldstr    aParentwelcome// "ParentWelcome"
0x87a52  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x87a57  ldstr    aParenttriggers// "ParentTriggers"
0x87a5c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x87a61  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::AddPageSelection(string precedingPage, string pageToAdd)
0x87a66  ldarg.0
0x87a67  ldstr    aParenttriggers// "ParentTriggers"
0x87a6c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x87a71  ldstr    aParentactions// "ParentActions"
0x87a76  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x87a7b  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::AddPageSelection(string precedingPage, string pageToAdd)
0x87a80  ldarg.0
0x87a81  ldstr    aParentactions// "ParentActions"
0x87a86  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x87a8b  ldstr    aParentfinish// "ParentFinish"
0x87a90  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x87a95  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::AddPageSelection(string precedingPage, string pageToAdd)
0x87a9a  ldarg.0
0x87a9b  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberPages
0x87aa0  ldarg.0
0x87aa1  ldarg.0
0x87aa2  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::ChildControlDataEntered(bool requiredDataExists)
0x87aa8  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ParentControlDataHandler::.ctor(object object, native int method)
0x87aad  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskGeneralControl::.ctor(class Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard wizardManager, class Microsoft.Windows.ManagementUI.CombinedControls.ParentControlDataHandler parentHandler)
0x87ab2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x87ab7  pop
0x87ab8  ldarg.0
0x87ab9  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberPages
0x87abe  ldarg.0
0x87abf  ldarg.0
0x87ac0  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::ChildControlDataEntered(bool requiredDataExists)
0x87ac6  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ParentControlDataHandler::.ctor(object object, native int method)
0x87acb  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.WizardTriggerHomeControl::.ctor(class Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard wizardManager, class Microsoft.Windows.ManagementUI.CombinedControls.ParentControlDataHandler parentHandler)
0x87ad0  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x87ad5  pop
0x87ad6  ldarg.0
0x87ad7  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberPages
0x87adc  ldarg.0
0x87add  ldarg.0
0x87ade  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::ChildControlDataEntered(bool requiredDataExists)
0x87ae4  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ParentControlDataHandler::.ctor(object object, native int method)
0x87ae9  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.WizardActionHomeControl::.ctor(class Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard wizardManager, class Microsoft.Windows.ManagementUI.CombinedControls.ParentControlDataHandler parentHandler)
0x87aee  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x87af3  pop
0x87af4  ldarg.0
0x87af5  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberPages
0x87afa  ldarg.0
0x87afb  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::.ctor(class Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard wizardManager)
0x87b00  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x87b05  pop
0x87b06  ldarg.0
0x87b07  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::ConfigureWizard()
0x87b0c  ldarg.0
0x87b0d  ldarg.0
0x87b0e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::nextBtn
0x87b13  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_AcceptButton(class [System.Windows.Forms]System.Windows.Forms.IButtonControl)
0x87b18  ret
```
