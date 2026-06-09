# System.Web.UI.Design.WebControls.LoginViewDesigner::get_TemplateDefinition

- ea: `0x29bc0`
- end: `0x29c25`
- name: `System.Web.UI.Design.WebControls.LoginViewDesigner::get_TemplateDefinition`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x29d40`

## callees

- `0x10240`
- `0x29b00`
- `0x29bc0`

## string_xrefs

- `0x29c02`: `ContentTemplate`
- `0x29c1a`: `ContentTemplate`
- `0x29bcb`: `AnonymousTemplate`
- `0x29bd6`: `AnonymousTemplate`
- `0x29beb`: `LoggedInTemplate`
- `0x29bf6`: `LoggedInTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x29bc0  ldarg.0
0x29bc1  call     instance int32 System.Web.UI.Design.WebControls.LoginViewDesigner::get_CurrentView()
0x29bc6  stloc.0
0x29bc7  ldloc.0
0x29bc8  brtrue.s loc_29BE1
0x29bca  ldarg.0
0x29bcb  ldstr    aAnonymoustempl// "AnonymousTemplate"
0x29bd0  ldarg.0
0x29bd1  ldfld    class [System.Web]System.Web.UI.WebControls.LoginView System.Web.UI.Design.WebControls.LoginViewDesigner::_loginView
0x29bd6  ldstr    aAnonymoustempl// "AnonymousTemplate"
0x29bdb  newobj   instance void System.Web.UI.Design.TemplateDefinition::.ctor(class System.Web.UI.Design.ControlDesigner designer, string name, object templatedObject, string templatePropertyName)
0x29be0  ret
0x29be1  ldarg.0
0x29be2  call     instance int32 System.Web.UI.Design.WebControls.LoginViewDesigner::get_CurrentView()
0x29be7  ldc.i4.1
0x29be8  bne.un.s loc_29C01
0x29bea  ldarg.0
0x29beb  ldstr    aLoggedintempla// "LoggedInTemplate"
0x29bf0  ldarg.0
0x29bf1  ldfld    class [System.Web]System.Web.UI.WebControls.LoginView System.Web.UI.Design.WebControls.LoginViewDesigner::_loginView
0x29bf6  ldstr    aLoggedintempla// "LoggedInTemplate"
0x29bfb  newobj   instance void System.Web.UI.Design.TemplateDefinition::.ctor(class System.Web.UI.Design.ControlDesigner designer, string name, object templatedObject, string templatePropertyName)
0x29c00  ret
0x29c01  ldarg.0
0x29c02  ldstr    aContenttemplat// "ContentTemplate"
0x29c07  ldarg.0
0x29c08  ldfld    class [System.Web]System.Web.UI.WebControls.LoginView System.Web.UI.Design.WebControls.LoginViewDesigner::_loginView
0x29c0d  callvirt instance class [System.Web]System.Web.UI.WebControls.RoleGroupCollection [System.Web]System.Web.UI.WebControls.LoginView::get_RoleGroups()
0x29c12  ldloc.0
0x29c13  ldc.i4.2
0x29c14  sub
0x29c15  callvirt instance class [System.Web]System.Web.UI.WebControls.RoleGroup [System.Web]System.Web.UI.WebControls.RoleGroupCollection::get_Item(int32)
0x29c1a  ldstr    aContenttemplat// "ContentTemplate"
0x29c1f  newobj   instance void System.Web.UI.Design.TemplateDefinition::.ctor(class System.Web.UI.Design.ControlDesigner designer, string name, object templatedObject, string templatePropertyName)
0x29c24  ret
```
