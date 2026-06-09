# Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::Initialize_1

- ea: `0x877d0`
- end: `0x878c2`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::Initialize_1`
- size: `242`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x87760`
- `0x877a0`

## callees

- `0x12ed0`
- `0x14500`
- `0x645d0`
- `0x86960`
- `0x87540`
- `0x87c40`
- `0x88a00`
- `0x89020`
- `0x89090`

## string_xrefs

- `0x877e0`: `ParentWelcome`
- `0x877f0`: `ParentWelcome`

## pseudocode

```c

```

## disassembly

```asm
0x877d0  ldarg.0
0x877d1  ldc.i4.2
0x877d2  stfld    valuetype TaskOwnerEnum Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::ownerOfTask
0x877d7  ldarg.0
0x877d8  ldarg.2
0x877d9  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::uiTaskFolder
0x877de  ldarg.0
0x877df  ldnull
0x877e0  ldstr    aParentwelcome// "ParentWelcome"
0x877e5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x877ea  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::AddPageSelection(string precedingPage, string pageToAdd)
0x877ef  ldarg.0
0x877f0  ldstr    aParentwelcome// "ParentWelcome"
0x877f5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x877fa  ldstr    aChildtriggerev// "ChildTriggerEvent"
0x877ff  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x87804  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::AddPageSelection(string precedingPage, string pageToAdd)
0x87809  ldarg.0
0x8780a  ldstr    aChildtriggerev// "ChildTriggerEvent"
0x8780f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x87814  ldstr    aParentactions// "ParentActions"
0x87819  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x8781e  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::AddPageSelection(string precedingPage, string pageToAdd)
0x87823  ldarg.0
0x87824  ldstr    aParentactions// "ParentActions"
0x87829  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x8782e  ldstr    aParentfinish// "ParentFinish"
0x87833  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x87838  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::AddPageSelection(string precedingPage, string pageToAdd)
0x8783d  ldarg.0
0x8783e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::uiTaskCurrentTask
0x87843  ldarg.3
0x87844  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITask::set_Name(string value)
0x87849  ldarg.0
0x8784a  ldarg.0
0x8784b  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::ChildControlDataEntered(bool requiredDataExists)
0x87851  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ParentControlDataHandler::.ctor(object object, native int method)
0x87856  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskGeneralControl::.ctor(class Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard wizardManager, class Microsoft.Windows.ManagementUI.CombinedControls.ParentControlDataHandler parentHandler)
0x8785b  stloc.0
0x8785c  ldloc.0
0x8785d  ldarg.3
0x8785e  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskGeneralControl::SetNameTextBox(string name)
0x87863  pop
0x87864  ldarg.0
0x87865  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberPages
0x8786a  ldloc.0
0x8786b  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x87870  pop
0x87871  ldarg.0
0x87872  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberPages
0x87877  ldarg.1
0x87878  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x8787d  pop
0x8787e  ldarg.0
0x8787f  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberPages
0x87884  ldarg.0
0x87885  ldarg.0
0x87886  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::ChildControlDataEntered(bool requiredDataExists)
0x8788c  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ParentControlDataHandler::.ctor(object object, native int method)
0x87891  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.WizardActionHomeControl::.ctor(class Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard wizardManager, class Microsoft.Windows.ManagementUI.CombinedControls.ParentControlDataHandler parentHandler)
0x87896  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x8789b  pop
0x8789c  ldarg.0
0x8789d  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::memberPages
0x878a2  ldarg.0
0x878a3  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::.ctor(class Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard wizardManager)
0x878a8  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x878ad  pop
0x878ae  ldarg.0
0x878af  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::ConfigureWizard()
0x878b4  ldarg.0
0x878b5  ldarg.0
0x878b6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::nextBtn
0x878bb  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_AcceptButton(class [System.Windows.Forms]System.Windows.Forms.IButtonControl)
0x878c0  ldc.i4.1
0x878c1  ret
```
