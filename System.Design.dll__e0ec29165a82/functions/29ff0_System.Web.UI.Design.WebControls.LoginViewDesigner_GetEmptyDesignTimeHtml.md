# System.Web.UI.Design.WebControls.LoginViewDesigner::GetEmptyDesignTimeHtml

- ea: `0x29ff0`
- end: `0x2a06c`
- name: `System.Web.UI.Design.WebControls.LoginViewDesigner::GetEmptyDesignTimeHtml`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x29c0`
- `0x29b00`
- `0x29d80`
- `0x29ff0`
- `0x8eec0`
- `0x8ef40`

## string_xrefs

- `0x2a006`: `LoginView_AnonymousTemplateEmpty`
- `0x2a013`: `LoginView_LoggedInTemplateEmpty`
- `0x2a03b`: `LoginView_RoleGroupTemplateEmpty`
- `0x2a057`: `LoginView_NoTemplateInst`

## pseudocode

```c

```

## disassembly

```asm
0x29ff0  ldsfld   string [mscorlib]System.String::Empty
0x29ff5  stloc.0
0x29ff6  ldarg.0
0x29ff7  call     instance int32 System.Web.UI.Design.WebControls.LoginViewDesigner::get_CurrentView()
0x29ffc  stloc.3
0x29ffd  ldloc.3
0x29ffe  brfalse.s loc_2A006
0x2a000  ldloc.3
0x2a001  ldc.i4.1
0x2a002  beq.s    loc_2A013
0x2a004  br.s     loc_2A020
0x2a006  ldstr    aLoginviewAnony// "LoginView_AnonymousTemplateEmpty"
0x2a00b  call     string System.Design.SR::GetString(string name)
0x2a010  stloc.0
0x2a011  br.s     loc_2A050
0x2a013  ldstr    aLoginviewLogge// "LoginView_LoggedInTemplateEmpty"
0x2a018  call     string System.Design.SR::GetString(string name)
0x2a01d  stloc.0
0x2a01e  br.s     loc_2A050
0x2a020  ldarg.0
0x2a021  call     instance int32 System.Web.UI.Design.WebControls.LoginViewDesigner::get_CurrentView()
0x2a026  ldc.i4.2
0x2a027  sub
0x2a028  stloc.1
0x2a029  ldloc.1
0x2a02a  ldarg.0
0x2a02b  ldfld    class [System.Web]System.Web.UI.WebControls.LoginView System.Web.UI.Design.WebControls.LoginViewDesigner::_loginView
0x2a030  callvirt instance class [System.Web]System.Web.UI.WebControls.RoleGroupCollection [System.Web]System.Web.UI.WebControls.LoginView::get_RoleGroups()
0x2a035  call     string System.Web.UI.Design.WebControls.LoginViewDesigner::CreateRoleGroupCaption(int32 roleGroupIndex, class [System.Web]System.Web.UI.WebControls.RoleGroupCollection roleGroups)
0x2a03a  stloc.2
0x2a03b  ldstr    aLoginviewRoleg// "LoginView_RoleGroupTemplateEmpty"
0x2a040  ldc.i4.1
0x2a041  newarr   [mscorlib]System.Object
0x2a046  dup
0x2a047  ldc.i4.0
0x2a048  ldloc.2
0x2a049  stelem.ref
0x2a04a  call     string System.Design.SR::GetString(string name, object[] args)
0x2a04f  stloc.0
0x2a050  ldarg.0
0x2a051  ldloc.0
0x2a052  ldstr    aBr_1// "<br>"
0x2a057  ldstr    aLoginviewNotem// "LoginView_NoTemplateInst"
0x2a05c  call     string System.Design.SR::GetString(string name)
0x2a061  call     string [mscorlib]System.String::Concat(string, string, string)
0x2a066  call     instance string System.Web.UI.Design.ControlDesigner::CreatePlaceHolderDesignTimeHtml(string instruction)
0x2a06b  ret
```
