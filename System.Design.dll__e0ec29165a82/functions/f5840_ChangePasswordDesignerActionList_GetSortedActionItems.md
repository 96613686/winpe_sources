# ChangePasswordDesignerActionList::GetSortedActionItems

- ea: `0xf5840`
- end: `0xf590c`
- name: `ChangePasswordDesignerActionList::GetSortedActionItems`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x183a0`
- `0x593e0`
- `0x598e0`
- `0x5af90`
- `0x5d870`
- `0x5d8b0`
- `0x8ef40`
- `0xf5840`

## string_xrefs

- `0xf58b9`: `WebControls_ConvertToTemplate`
- `0xf58b4`: `ConvertToTemplate`
- `0xf58c8`: `WebControls_ConvertToTemplateDescriptionViews`

## pseudocode

```c

```

## disassembly

```asm
0xf5840  newobj   instance void System.ComponentModel.Design.DesignerActionItemCollection::.ctor()
0xf5845  stloc.0
0xf5846  ldloc.0
0xf5847  ldstr    aView// "View"
0xf584c  ldstr    aWebcontrolsVie// "WebControls_Views"
0xf5851  call     string System.Design.SR::GetString(string name)
0xf5856  ldsfld   string [mscorlib]System.String::Empty
0xf585b  ldstr    aWebcontrolsVie_0// "WebControls_ViewsDescription"
0xf5860  call     string System.Design.SR::GetString(string name)
0xf5865  newobj   instance void System.ComponentModel.Design.DesignerActionPropertyItem::.ctor(string memberName, string displayName, string category, string description)
0xf586a  dup
0xf586b  ldc.i4.0
0xf586c  callvirt instance void System.ComponentModel.Design.DesignerActionItem::set_ShowInSourceView(bool value)
0xf5871  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf5876  pop
0xf5877  ldarg.0
0xf5878  ldfld    class System.Web.UI.Design.WebControls.ChangePasswordDesigner ChangePasswordDesignerActionList::_designer
0xf587d  callvirt instance bool System.Web.UI.Design.WebControls.ChangePasswordDesigner::get_Templated()
0xf5882  brfalse.s loc_F58B2
0xf5884  ldloc.0
0xf5885  ldarg.0
0xf5886  ldstr    aReset// "Reset"
0xf588b  ldstr    aWebcontrolsRes// "WebControls_Reset"
0xf5890  call     string System.Design.SR::GetString(string name)
0xf5895  ldsfld   string [mscorlib]System.String::Empty
0xf589a  ldstr    aWebcontrolsRes_0// "WebControls_ResetDescriptionViews"
0xf589f  call     string System.Design.SR::GetString(string name)
0xf58a4  ldc.i4.1
0xf58a5  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf58aa  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf58af  pop
0xf58b0  br.s     loc_F58DE
0xf58b2  ldloc.0
0xf58b3  ldarg.0
0xf58b4  ldstr    aConverttotempl// "ConvertToTemplate"
0xf58b9  ldstr    aWebcontrolsCon// "WebControls_ConvertToTemplate"
0xf58be  call     string System.Design.SR::GetString(string name)
0xf58c3  ldsfld   string [mscorlib]System.String::Empty
0xf58c8  ldstr    aWebcontrolsCon_0// "WebControls_ConvertToTemplateDescriptio"...
0xf58cd  call     string System.Design.SR::GetString(string name)
0xf58d2  ldc.i4.1
0xf58d3  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf58d8  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf58dd  pop
0xf58de  ldloc.0
0xf58df  ldarg.0
0xf58e0  ldstr    aLaunchwebadmin// "LaunchWebAdmin"
0xf58e5  ldstr    aLoginLaunchweb// "Login_LaunchWebAdmin"
0xf58ea  call     string System.Design.SR::GetString(string name)
0xf58ef  ldsfld   string [mscorlib]System.String::Empty
0xf58f4  ldstr    aLoginLaunchweb_0// "Login_LaunchWebAdminDescription"
0xf58f9  call     string System.Design.SR::GetString(string name)
0xf58fe  ldc.i4.1
0xf58ff  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf5904  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf5909  pop
0xf590a  ldloc.0
0xf590b  ret
```
