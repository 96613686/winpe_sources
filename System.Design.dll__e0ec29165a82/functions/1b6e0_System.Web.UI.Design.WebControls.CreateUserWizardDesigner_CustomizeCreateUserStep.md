# System.Web.UI.Design.WebControls.CreateUserWizardDesigner::CustomizeCreateUserStep

- ea: `0x1b6e0`
- end: `0x1b790`
- name: `System.Web.UI.Design.WebControls.CreateUserWizardDesigner::CustomizeCreateUserStep`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0xf5e60`

## callees

- `0x32a0`
- `0x32c0`
- `0x11680`
- `0x584f0`
- `0x8eec0`
- `0x8ef40`

## string_xrefs

- `0x1b75b`: `ContentTemplate`
- `0x1b736`: `CreateUserWizard_NavigateToStep`
- `0x1b77f`: `CreateUserWizard_CustomizeCreateUserStep`

## pseudocode

```c

```

## disassembly

```asm
0x1b6e0  ldarg.0
0x1b6e1  ldfld    class [System.Web]System.Web.UI.WebControls.CreateUserWizard System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_createUserWizard
0x1b6e6  callvirt instance class [System.Web]System.Web.UI.WebControls.CreateUserWizardStep [System.Web]System.Web.UI.WebControls.CreateUserWizard::get_CreateUserStep()
0x1b6eb  stloc.0
0x1b6ec  ldarg.0
0x1b6ed  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x1b6f2  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x1b6f7  ldstr    aActivestepinde// "ActiveStepIndex"
0x1b6fc  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x1b701  stloc.1
0x1b702  ldarg.0
0x1b703  ldfld    class [System.Web]System.Web.UI.WebControls.CreateUserWizard System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_createUserWizard
0x1b708  callvirt instance class [System.Web]System.Web.UI.WebControls.WizardStepCollection [System.Web]System.Web.UI.WebControls.Wizard::get_WizardSteps()
0x1b70d  ldarg.0
0x1b70e  ldfld    class [System.Web]System.Web.UI.WebControls.CreateUserWizard System.Web.UI.Design.WebControls.CreateUserWizardDesigner::_createUserWizard
0x1b713  callvirt instance class [System.Web]System.Web.UI.WebControls.CreateUserWizardStep [System.Web]System.Web.UI.WebControls.CreateUserWizard::get_CreateUserStep()
0x1b718  callvirt instance int32 [System.Web]System.Web.UI.WebControls.WizardStepCollection::IndexOf(class [System.Web]System.Web.UI.WebControls.WizardStepBase)
0x1b71d  stloc.2
0x1b71e  ldarg.0
0x1b71f  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x1b724  ldarg.0
0x1b725  ldftn    instance bool System.Web.UI.Design.WebControls.CreateUserWizardDesigner::NavigateToStep(object context)
0x1b72b  newobj   instance void System.Web.UI.Design.TransactedChangeCallback::.ctor(object object, native int method)
0x1b730  ldloc.2
0x1b731  box      [mscorlib]System.Int32
0x1b736  ldstr    aCreateuserwiza_5// "CreateUserWizard_NavigateToStep"
0x1b73b  ldc.i4.1
0x1b73c  newarr   [mscorlib]System.Object
0x1b741  dup
0x1b742  ldc.i4.0
0x1b743  ldloc.2
0x1b744  box      [mscorlib]System.Int32
0x1b749  stelem.ref
0x1b74a  call     string System.Design.SR::GetString(string name, object[] args)
0x1b74f  ldloc.1
0x1b750  call     void System.Web.UI.Design.ControlDesigner::InvokeTransactedChange(class [System]System.ComponentModel.IComponent component, class System.Web.UI.Design.TransactedChangeCallback callback, object context, string description, class [System]System.ComponentModel.MemberDescriptor member)
0x1b755  ldloc.0
0x1b756  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x1b75b  ldstr    aContenttemplat// "ContentTemplate"
0x1b760  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x1b765  stloc.3
0x1b766  ldarg.0
0x1b767  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x1b76c  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x1b771  ldloc.0
0x1b772  ldarg.0
0x1b773  ldftn    instance bool System.Web.UI.Design.WebControls.CreateUserWizardDesigner::CustomizeCreateUserStepCallback(object context)
0x1b779  newobj   instance void System.Web.UI.Design.TransactedChangeCallback::.ctor(object object, native int method)
0x1b77e  ldnull
0x1b77f  ldstr    aCreateuserwiza_7// "CreateUserWizard_CustomizeCreateUserSte"...
0x1b784  call     string System.Design.SR::GetString(string name)
0x1b789  ldloc.3
0x1b78a  call     void System.Web.UI.Design.ControlDesigner::InvokeTransactedChange(class [mscorlib]System.IServiceProvider serviceProvider, class [System]System.ComponentModel.IComponent component, class System.Web.UI.Design.TransactedChangeCallback callback, object context, string description, class [System]System.ComponentModel.MemberDescriptor member)
0x1b78f  ret
```
