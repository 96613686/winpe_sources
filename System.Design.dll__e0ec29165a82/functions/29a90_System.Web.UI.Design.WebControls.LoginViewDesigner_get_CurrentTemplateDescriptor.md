# System.Web.UI.Design.WebControls.LoginViewDesigner::get_CurrentTemplateDescriptor

- ea: `0x29a90`
- end: `0x29af7`
- name: `System.Web.UI.Design.WebControls.LoginViewDesigner::get_CurrentTemplateDescriptor`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x29d40`

## callees

- `0x29a90`
- `0x29b00`
- `0x584f0`

## string_xrefs

- `0x29aec`: `ContentTemplate`
- `0x29aa3`: `AnonymousTemplate`
- `0x29ac2`: `LoggedInTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x29a90  ldarg.0
0x29a91  call     instance int32 System.Web.UI.Design.WebControls.LoginViewDesigner::get_CurrentView()
0x29a96  brtrue.s loc_29AAE
0x29a98  ldarg.0
0x29a99  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x29a9e  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x29aa3  ldstr    aAnonymoustempl// "AnonymousTemplate"
0x29aa8  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x29aad  ret
0x29aae  ldarg.0
0x29aaf  call     instance int32 System.Web.UI.Design.WebControls.LoginViewDesigner::get_CurrentView()
0x29ab4  ldc.i4.1
0x29ab5  bne.un.s loc_29ACD
0x29ab7  ldarg.0
0x29ab8  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x29abd  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x29ac2  ldstr    aLoggedintempla// "LoggedInTemplate"
0x29ac7  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x29acc  ret
0x29acd  ldarg.0
0x29ace  ldfld    class [System.Web]System.Web.UI.WebControls.LoginView System.Web.UI.Design.WebControls.LoginViewDesigner::_loginView
0x29ad3  callvirt instance class [System.Web]System.Web.UI.WebControls.RoleGroupCollection [System.Web]System.Web.UI.WebControls.LoginView::get_RoleGroups()
0x29ad8  ldarg.0
0x29ad9  call     instance int32 System.Web.UI.Design.WebControls.LoginViewDesigner::get_CurrentView()
0x29ade  ldc.i4.2
0x29adf  sub
0x29ae0  callvirt instance class [System.Web]System.Web.UI.WebControls.RoleGroup [System.Web]System.Web.UI.WebControls.RoleGroupCollection::get_Item(int32)
0x29ae5  stloc.0
0x29ae6  ldloc.0
0x29ae7  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x29aec  ldstr    aContenttemplat// "ContentTemplate"
0x29af1  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x29af6  ret
```
