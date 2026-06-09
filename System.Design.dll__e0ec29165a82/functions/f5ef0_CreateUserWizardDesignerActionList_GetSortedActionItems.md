# CreateUserWizardDesignerActionList::GetSortedActionItems

- ea: `0xf5ef0`
- end: `0xf6019`
- name: `CreateUserWizardDesignerActionList::GetSortedActionItems`
- size: `297`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x2660`
- `0x598e0`
- `0x5d870`
- `0x5d8b0`
- `0x8ef40`
- `0xf5ef0`

## string_xrefs

- `0xf5f98`: `CreateUserWizard_CustomizeCompleteStep`
- `0xf5f27`: `CreateUserWizard_CustomizeCreateUserStep`
- `0xf5fc6`: `CreateUserWizard_ResetCompleteStepVerb`
- `0xf5f55`: `CreateUserWizard_ResetCreateUserStepVerb`
- `0xf5f22`: `CustomizeCreateUserStep`
- `0xf5f36`: `CreateUserWizard_CustomizeCreateUserStepDescription`
- `0xf5f50`: `ResetCreateUserStep`
- `0xf5f64`: `CreateUserWizard_ResetCreateUserStepVerbDescription`
- `0xf5f93`: `CustomizeCompleteStep`
- `0xf5fa7`: `CreateUserWizard_CustomizeCompleteStepDescription`
- `0xf5fc1`: `ResetCompleteStep`
- `0xf5fd5`: `CreateUserWizard_ResetCompleteStepVerbDescription`

## pseudocode

```c

```

## disassembly

```asm
0xf5ef0  ldarg.0
0xf5ef1  ldfld    class System.Web.UI.Design.WebControls.CreateUserWizardDesigner CreateUserWizardDesignerActionList::_parent
0xf5ef6  callvirt instance bool System.Web.UI.Design.ControlDesigner::get_InTemplateMode()
0xf5efb  brfalse.s loc_F5F03
0xf5efd  newobj   instance void System.ComponentModel.Design.DesignerActionItemCollection::.ctor()
0xf5f02  ret
0xf5f03  newobj   instance void System.ComponentModel.Design.DesignerActionItemCollection::.ctor()
0xf5f08  stloc.0
0xf5f09  ldarg.0
0xf5f0a  ldfld    class System.Web.UI.Design.WebControls.CreateUserWizardDesigner CreateUserWizardDesignerActionList::_parent
0xf5f0f  ldfld    class [System.Web]System.Web.UI.WebControls.CreateUserWizard System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_createUserWizard
0xf5f14  callvirt instance class [System.Web]System.Web.UI.WebControls.CreateUserWizardStep [System.Web]System.Web.UI.WebControls.CreateUserWizard::get_CreateUserStep()
0xf5f19  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.TemplatedWizardStep::get_ContentTemplate()
0xf5f1e  brtrue.s loc_F5F4E
0xf5f20  ldloc.0
0xf5f21  ldarg.0
0xf5f22  ldstr    aCustomizecreat// "CustomizeCreateUserStep"
0xf5f27  ldstr    aCreateuserwiza_7// "CreateUserWizard_CustomizeCreateUserSte"...
0xf5f2c  call     string System.Design.SR::GetString(string name)
0xf5f31  ldsfld   string [mscorlib]System.String::Empty
0xf5f36  ldstr    aCreateuserwiza_11// "CreateUserWizard_CustomizeCreateUserSte"...
0xf5f3b  call     string System.Design.SR::GetString(string name)
0xf5f40  ldc.i4.1
0xf5f41  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf5f46  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf5f4b  pop
0xf5f4c  br.s     loc_F5F7A
0xf5f4e  ldloc.0
0xf5f4f  ldarg.0
0xf5f50  ldstr    aResetcreateuse// "ResetCreateUserStep"
0xf5f55  ldstr    aCreateuserwiza_9// "CreateUserWizard_ResetCreateUserStepVer"...
0xf5f5a  call     string System.Design.SR::GetString(string name)
0xf5f5f  ldsfld   string [mscorlib]System.String::Empty
0xf5f64  ldstr    aCreateuserwiza_12// "CreateUserWizard_ResetCreateUserStepVer"...
0xf5f69  call     string System.Design.SR::GetString(string name)
0xf5f6e  ldc.i4.1
0xf5f6f  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf5f74  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf5f79  pop
0xf5f7a  ldarg.0
0xf5f7b  ldfld    class System.Web.UI.Design.WebControls.CreateUserWizardDesigner CreateUserWizardDesignerActionList::_parent
0xf5f80  ldfld    class [System.Web]System.Web.UI.WebControls.CreateUserWizard System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_createUserWizard
0xf5f85  callvirt instance class [System.Web]System.Web.UI.WebControls.CompleteWizardStep [System.Web]System.Web.UI.WebControls.CreateUserWizard::get_CompleteStep()
0xf5f8a  callvirt instance class [System.Web]System.Web.UI.ITemplate [System.Web]System.Web.UI.WebControls.TemplatedWizardStep::get_ContentTemplate()
0xf5f8f  brtrue.s loc_F5FBF
0xf5f91  ldloc.0
0xf5f92  ldarg.0
0xf5f93  ldstr    aCustomizecompl// "CustomizeCompleteStep"
0xf5f98  ldstr    aCreateuserwiza_6// "CreateUserWizard_CustomizeCompleteStep"
0xf5f9d  call     string System.Design.SR::GetString(string name)
0xf5fa2  ldsfld   string [mscorlib]System.String::Empty
0xf5fa7  ldstr    aCreateuserwiza_13// "CreateUserWizard_CustomizeCompleteStepD"...
0xf5fac  call     string System.Design.SR::GetString(string name)
0xf5fb1  ldc.i4.1
0xf5fb2  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf5fb7  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf5fbc  pop
0xf5fbd  br.s     loc_F5FEB
0xf5fbf  ldloc.0
0xf5fc0  ldarg.0
0xf5fc1  ldstr    aResetcompletes// "ResetCompleteStep"
0xf5fc6  ldstr    aCreateuserwiza_8// "CreateUserWizard_ResetCompleteStepVerb"
0xf5fcb  call     string System.Design.SR::GetString(string name)
0xf5fd0  ldsfld   string [mscorlib]System.String::Empty
0xf5fd5  ldstr    aCreateuserwiza_14// "CreateUserWizard_ResetCompleteStepVerbD"...
0xf5fda  call     string System.Design.SR::GetString(string name)
0xf5fdf  ldc.i4.1
0xf5fe0  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf5fe5  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf5fea  pop
0xf5feb  ldloc.0
0xf5fec  ldarg.0
0xf5fed  ldstr    aLaunchwebadmin// "LaunchWebAdmin"
0xf5ff2  ldstr    aLoginLaunchweb// "Login_LaunchWebAdmin"
0xf5ff7  call     string System.Design.SR::GetString(string name)
0xf5ffc  ldsfld   string [mscorlib]System.String::Empty
0xf6001  ldstr    aLoginLaunchweb_0// "Login_LaunchWebAdminDescription"
0xf6006  call     string System.Design.SR::GetString(string name)
0xf600b  ldc.i4.1
0xf600c  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf6011  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf6016  pop
0xf6017  ldloc.0
0xf6018  ret
```
