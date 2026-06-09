# System.Web.UI.Design.WebControls.LoginViewDesigner::get_TemplateGroups

- ea: `0x29c30`
- end: `0x29d22`
- name: `System.Web.UI.Design.WebControls.LoginViewDesigner::get_TemplateGroups`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x27f0`
- `0x10240`
- `0x10ff0`
- `0x11090`
- `0x110e0`
- `0x11170`
- `0x11180`
- `0x29c30`
- `0x29d80`

## string_xrefs

- `0x29ceb`: `ContentTemplate`
- `0x29c4d`: `AnonymousTemplate`
- `0x29c5a`: `AnonymousTemplate`
- `0x29c65`: `AnonymousTemplate`
- `0x29c81`: `LoggedInTemplate`
- `0x29c8e`: `LoggedInTemplate`
- `0x29c99`: `LoggedInTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x29c30  ldarg.0
0x29c31  call     instance class System.Web.UI.Design.TemplateGroupCollection System.Web.UI.Design.ControlDesigner::get_TemplateGroups()
0x29c36  stloc.0
0x29c37  ldarg.0
0x29c38  ldfld    class System.Web.UI.Design.TemplateGroupCollection System.Web.UI.Design.WebControls.LoginViewDesigner::_templateGroups
0x29c3d  brtrue   loc_29D14
0x29c42  ldarg.0
0x29c43  newobj   instance void System.Web.UI.Design.TemplateGroupCollection::.ctor()
0x29c48  stfld    class System.Web.UI.Design.TemplateGroupCollection System.Web.UI.Design.WebControls.LoginViewDesigner::_templateGroups
0x29c4d  ldstr    aAnonymoustempl// "AnonymousTemplate"
0x29c52  newobj   instance void System.Web.UI.Design.TemplateGroup::.ctor(string groupName)
0x29c57  stloc.1
0x29c58  ldloc.1
0x29c59  ldarg.0
0x29c5a  ldstr    aAnonymoustempl// "AnonymousTemplate"
0x29c5f  ldarg.0
0x29c60  ldfld    class [System.Web]System.Web.UI.WebControls.LoginView System.Web.UI.Design.WebControls.LoginViewDesigner::_loginView
0x29c65  ldstr    aAnonymoustempl// "AnonymousTemplate"
0x29c6a  newobj   instance void System.Web.UI.Design.TemplateDefinition::.ctor(class System.Web.UI.Design.ControlDesigner designer, string name, object templatedObject, string templatePropertyName)
0x29c6f  callvirt instance void System.Web.UI.Design.TemplateGroup::AddTemplateDefinition(class System.Web.UI.Design.TemplateDefinition templateDefinition)
0x29c74  ldarg.0
0x29c75  ldfld    class System.Web.UI.Design.TemplateGroupCollection System.Web.UI.Design.WebControls.LoginViewDesigner::_templateGroups
0x29c7a  ldloc.1
0x29c7b  callvirt instance int32 System.Web.UI.Design.TemplateGroupCollection::Add(class System.Web.UI.Design.TemplateGroup group)
0x29c80  pop
0x29c81  ldstr    aLoggedintempla// "LoggedInTemplate"
0x29c86  newobj   instance void System.Web.UI.Design.TemplateGroup::.ctor(string groupName)
0x29c8b  stloc.1
0x29c8c  ldloc.1
0x29c8d  ldarg.0
0x29c8e  ldstr    aLoggedintempla// "LoggedInTemplate"
0x29c93  ldarg.0
0x29c94  ldfld    class [System.Web]System.Web.UI.WebControls.LoginView System.Web.UI.Design.WebControls.LoginViewDesigner::_loginView
0x29c99  ldstr    aLoggedintempla// "LoggedInTemplate"
0x29c9e  newobj   instance void System.Web.UI.Design.TemplateDefinition::.ctor(class System.Web.UI.Design.ControlDesigner designer, string name, object templatedObject, string templatePropertyName)
0x29ca3  callvirt instance void System.Web.UI.Design.TemplateGroup::AddTemplateDefinition(class System.Web.UI.Design.TemplateDefinition templateDefinition)
0x29ca8  ldarg.0
0x29ca9  ldfld    class System.Web.UI.Design.TemplateGroupCollection System.Web.UI.Design.WebControls.LoginViewDesigner::_templateGroups
0x29cae  ldloc.1
0x29caf  callvirt instance int32 System.Web.UI.Design.TemplateGroupCollection::Add(class System.Web.UI.Design.TemplateGroup group)
0x29cb4  pop
0x29cb5  ldarg.0
0x29cb6  ldfld    class [System.Web]System.Web.UI.WebControls.LoginView System.Web.UI.Design.WebControls.LoginViewDesigner::_loginView
0x29cbb  callvirt instance class [System.Web]System.Web.UI.WebControls.RoleGroupCollection [System.Web]System.Web.UI.WebControls.LoginView::get_RoleGroups()
0x29cc0  stloc.2
0x29cc1  ldc.i4.0
0x29cc2  stloc.3
0x29cc3  br.s     loc_29D0B
0x29cc5  ldloc.3
0x29cc6  ldloc.2
0x29cc7  call     string System.Web.UI.Design.WebControls.LoginViewDesigner::CreateRoleGroupCaption(int32 roleGroupIndex, class [System.Web]System.Web.UI.WebControls.RoleGroupCollection roleGroups)
0x29ccc  stloc.s  4
0x29cce  ldloc.s  4
0x29cd0  newobj   instance void System.Web.UI.Design.TemplateGroup::.ctor(string groupName)
0x29cd5  stloc.1
0x29cd6  ldloc.1
0x29cd7  ldarg.0
0x29cd8  ldloc.s  4
0x29cda  ldarg.0
0x29cdb  ldfld    class [System.Web]System.Web.UI.WebControls.LoginView System.Web.UI.Design.WebControls.LoginViewDesigner::_loginView
0x29ce0  callvirt instance class [System.Web]System.Web.UI.WebControls.RoleGroupCollection [System.Web]System.Web.UI.WebControls.LoginView::get_RoleGroups()
0x29ce5  ldloc.3
0x29ce6  callvirt instance class [System.Web]System.Web.UI.WebControls.RoleGroup [System.Web]System.Web.UI.WebControls.RoleGroupCollection::get_Item(int32)
0x29ceb  ldstr    aContenttemplat// "ContentTemplate"
0x29cf0  newobj   instance void System.Web.UI.Design.TemplateDefinition::.ctor(class System.Web.UI.Design.ControlDesigner designer, string name, object templatedObject, string templatePropertyName)
0x29cf5  callvirt instance void System.Web.UI.Design.TemplateGroup::AddTemplateDefinition(class System.Web.UI.Design.TemplateDefinition templateDefinition)
0x29cfa  ldarg.0
0x29cfb  ldfld    class System.Web.UI.Design.TemplateGroupCollection System.Web.UI.Design.WebControls.LoginViewDesigner::_templateGroups
0x29d00  ldloc.1
0x29d01  callvirt instance int32 System.Web.UI.Design.TemplateGroupCollection::Add(class System.Web.UI.Design.TemplateGroup group)
0x29d06  pop
0x29d07  ldloc.3
0x29d08  ldc.i4.1
0x29d09  add
0x29d0a  stloc.3
0x29d0b  ldloc.3
0x29d0c  ldloc.2
0x29d0d  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x29d12  blt.s    loc_29CC5
0x29d14  ldloc.0
0x29d15  ldarg.0
0x29d16  ldfld    class System.Web.UI.Design.TemplateGroupCollection System.Web.UI.Design.WebControls.LoginViewDesigner::_templateGroups
0x29d1b  callvirt instance void System.Web.UI.Design.TemplateGroupCollection::AddRange(class System.Web.UI.Design.TemplateGroupCollection groups)
0x29d20  ldloc.0
0x29d21  ret
```
