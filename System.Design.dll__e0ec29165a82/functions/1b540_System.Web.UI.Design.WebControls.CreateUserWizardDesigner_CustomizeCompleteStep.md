# System.Web.UI.Design.WebControls.CreateUserWizardDesigner::CustomizeCompleteStep

- ea: `0x1b540`
- end: `0x1b5f0`
- name: `System.Web.UI.Design.WebControls.CreateUserWizardDesigner::CustomizeCompleteStep`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xf5e90`

## callees

- `0x32a0`
- `0x32c0`
- `0x11680`
- `0x584f0`
- `0x8eec0`
- `0x8ef40`

## string_xrefs

- `0x1b5bb`: `ContentTemplate`
- `0x1b596`: `CreateUserWizard_NavigateToStep`
- `0x1b5df`: `CreateUserWizard_CustomizeCompleteStep`

## pseudocode

```c

```

## disassembly

```asm
0x1b540  ldarg.0
0x1b541  ldfld    class [System.Web]System.Web.UI.WebControls.CreateUserWizard System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_createUserWizard
0x1b546  callvirt instance class [System.Web]System.Web.UI.WebControls.CompleteWizardStep [System.Web]System.Web.UI.WebControls.CreateUserWizard::get_CompleteStep()
0x1b54b  stloc.0
0x1b54c  ldarg.0
0x1b54d  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x1b552  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x1b557  ldstr    aActivestepinde// "ActiveStepIndex"
0x1b55c  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x1b561  stloc.1
0x1b562  ldarg.0
0x1b563  ldfld    class [System.Web]System.Web.UI.WebControls.CreateUserWizard System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_createUserWizard
0x1b568  callvirt instance class [System.Web]System.Web.UI.WebControls.WizardStepCollection [System.Web]System.Web.UI.WebControls.Wizard::get_WizardSteps()
0x1b56d  ldarg.0
0x1b56e  ldfld    class [System.Web]System.Web.UI.WebControls.CreateUserWizard System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_createUserWizard
0x1b573  callvirt instance class [System.Web]System.Web.UI.WebControls.CompleteWizardStep [System.Web]System.Web.UI.WebControls.CreateUserWizard::get_CompleteStep()
0x1b578  callvirt instance int32 [System.Web]System.Web.UI.WebControls.WizardStepCollection::IndexOf(class [System.Web]System.Web.UI.WebControls.WizardStepBase)
0x1b57d  stloc.2
0x1b57e  ldarg.0
0x1b57f  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x1b584  ldarg.0
0x1b585  ldftn    instance bool System.Web.UI.Design.WebControls.CreateUserWizardDesigner::NavigateToStep(object context)
0x1b58b  newobj   instance void System.Web.UI.Design.TransactedChangeCallback::.ctor(object object, native int method)
0x1b590  ldloc.2
0x1b591  box      [mscorlib]System.Int32
0x1b596  ldstr    aCreateuserwiza_5// "CreateUserWizard_NavigateToStep"
0x1b59b  ldc.i4.1
0x1b59c  newarr   [mscorlib]System.Object
0x1b5a1  dup
0x1b5a2  ldc.i4.0
0x1b5a3  ldloc.2
0x1b5a4  box      [mscorlib]System.Int32
0x1b5a9  stelem.ref
0x1b5aa  call     string System.Design.SR::GetString(string name, object[] args)
0x1b5af  ldloc.1
0x1b5b0  call     void System.Web.UI.Design.ControlDesigner::InvokeTransactedChange(class [System]System.ComponentModel.IComponent component, class System.Web.UI.Design.TransactedChangeCallback callback, object context, string description, class [System]System.ComponentModel.MemberDescriptor member)
0x1b5b5  ldloc.0
0x1b5b6  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x1b5bb  ldstr    aContenttemplat// "ContentTemplate"
0x1b5c0  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x1b5c5  stloc.3
0x1b5c6  ldarg.0
0x1b5c7  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x1b5cc  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x1b5d1  ldloc.0
0x1b5d2  ldarg.0
0x1b5d3  ldftn    instance bool System.Web.UI.Design.WebControls.CreateUserWizardDesigner::CustomizeCompleteStepCallback(object context)
0x1b5d9  newobj   instance void System.Web.UI.Design.TransactedChangeCallback::.ctor(object object, native int method)
0x1b5de  ldnull
0x1b5df  ldstr    aCreateuserwiza_6// "CreateUserWizard_CustomizeCompleteStep"
0x1b5e4  call     string System.Design.SR::GetString(string name)
0x1b5e9  ldloc.3
0x1b5ea  call     void System.Web.UI.Design.ControlDesigner::InvokeTransactedChange(class [mscorlib]System.IServiceProvider serviceProvider, class [System]System.ComponentModel.IComponent component, class System.Web.UI.Design.TransactedChangeCallback callback, object context, string description, class [System]System.ComponentModel.MemberDescriptor member)
0x1b5ef  ret
```
