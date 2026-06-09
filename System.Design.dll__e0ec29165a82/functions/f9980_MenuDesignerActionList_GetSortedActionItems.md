# MenuDesignerActionList::GetSortedActionItems

- ea: `0xf9980`
- end: `0xf9ae2`
- name: `MenuDesignerActionList::GetSortedActionItems`
- size: `354`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x15380`
- `0x2b900`
- `0x2b910`
- `0x593e0`
- `0x598e0`
- `0x5af90`
- `0x5d870`
- `0x5d8b0`
- `0x8ef40`
- `0xf9980`

## string_xrefs

- `0xf9a60`: `MenuDesigner_ConvertToDynamicTemplate`
- `0xf9abf`: `MenuDesigner_ConvertToStaticTemplate`
- `0xf9a36`: `MenuDesigner_ResetDynamicTemplate`
- `0xf9a95`: `MenuDesigner_ResetStaticTemplate`
- `0xf9a31`: `ResetDynamicTemplate`
- `0xf9a41`: `MenuDesigner_ResetDynamicTemplateDescription`
- `0xf9a5b`: `ConvertToDynamicTemplate`
- `0xf9a6b`: `MenuDesigner_ConvertToDynamicTemplateDescription`
- `0xf9a90`: `ResetStaticTemplate`
- `0xf9aa0`: `MenuDesigner_ResetStaticTemplateDescription`
- `0xf9aba`: `ConvertToStaticTemplate`
- `0xf9aca`: `MenuDesigner_ConvertToStaticTemplateDescription`

## pseudocode

```c

```

## disassembly

```asm
0xf9980  newobj   instance void System.ComponentModel.Design.DesignerActionItemCollection::.ctor()
0xf9985  stloc.0
0xf9986  ldstr    aMenudesignerDa// "MenuDesigner_DataActionGroup"
0xf998b  call     string System.Design.SR::GetString(string name)
0xf9990  stloc.1
0xf9991  ldloc.0
0xf9992  ldstr    aView// "View"
0xf9997  ldstr    aWebcontrolsVie// "WebControls_Views"
0xf999c  call     string System.Design.SR::GetString(string name)
0xf99a1  ldloc.1
0xf99a2  ldstr    aMenudesignerVi// "MenuDesigner_ViewsDescription"
0xf99a7  call     string System.Design.SR::GetString(string name)
0xf99ac  newobj   instance void System.ComponentModel.Design.DesignerActionPropertyItem::.ctor(string memberName, string displayName, string category, string description)
0xf99b1  dup
0xf99b2  ldc.i4.0
0xf99b3  callvirt instance void System.ComponentModel.Design.DesignerActionItem::set_ShowInSourceView(bool value)
0xf99b8  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf99bd  pop
0xf99be  ldarg.0
0xf99bf  ldfld    class System.Web.UI.Design.WebControls.MenuDesigner MenuDesignerActionList::_parent
0xf99c4  callvirt instance string System.Web.UI.Design.WebControls.BaseDataBoundControlDesigner::get_DataSourceID()
0xf99c9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf99ce  brfalse.s loc_F99FA
0xf99d0  ldloc.0
0xf99d1  ldarg.0
0xf99d2  ldstr    aEditmenuitems// "EditMenuItems"
0xf99d7  ldstr    aMenudesignerEd_1// "MenuDesigner_EditMenuItems"
0xf99dc  call     string System.Design.SR::GetString(string name)
0xf99e1  ldloc.1
0xf99e2  ldstr    aMenudesignerEd_2// "MenuDesigner_EditMenuItemsDescription"
0xf99e7  call     string System.Design.SR::GetString(string name)
0xf99ec  ldc.i4.1
0xf99ed  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf99f2  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf99f7  pop
0xf99f8  br.s     loc_F9A22
0xf99fa  ldloc.0
0xf99fb  ldarg.0
0xf99fc  ldstr    aEditbindings// "EditBindings"
0xf9a01  ldstr    aMenudesignerEd_3// "MenuDesigner_EditBindings"
0xf9a06  call     string System.Design.SR::GetString(string name)
0xf9a0b  ldloc.1
0xf9a0c  ldstr    aMenudesignerEd_4// "MenuDesigner_EditBindingsDescription"
0xf9a11  call     string System.Design.SR::GetString(string name)
0xf9a16  ldc.i4.1
0xf9a17  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf9a1c  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf9a21  pop
0xf9a22  ldarg.0
0xf9a23  ldfld    class System.Web.UI.Design.WebControls.MenuDesigner MenuDesignerActionList::_parent
0xf9a28  callvirt instance bool System.Web.UI.Design.WebControls.MenuDesigner::get_DynamicTemplated()
0xf9a2d  brfalse.s loc_F9A59
0xf9a2f  ldloc.0
0xf9a30  ldarg.0
0xf9a31  ldstr    aResetdynamicte// "ResetDynamicTemplate"
0xf9a36  ldstr    aMenudesignerRe// "MenuDesigner_ResetDynamicTemplate"
0xf9a3b  call     string System.Design.SR::GetString(string name)
0xf9a40  ldloc.1
0xf9a41  ldstr    aMenudesignerRe_1// "MenuDesigner_ResetDynamicTemplateDescri"...
0xf9a46  call     string System.Design.SR::GetString(string name)
0xf9a4b  ldc.i4.1
0xf9a4c  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf9a51  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf9a56  pop
0xf9a57  br.s     loc_F9A81
0xf9a59  ldloc.0
0xf9a5a  ldarg.0
0xf9a5b  ldstr    aConverttodynam// "ConvertToDynamicTemplate"
0xf9a60  ldstr    aMenudesignerCo// "MenuDesigner_ConvertToDynamicTemplate"
0xf9a65  call     string System.Design.SR::GetString(string name)
0xf9a6a  ldloc.1
0xf9a6b  ldstr    aMenudesignerCo_1// "MenuDesigner_ConvertToDynamicTemplateDe"...
0xf9a70  call     string System.Design.SR::GetString(string name)
0xf9a75  ldc.i4.1
0xf9a76  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf9a7b  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf9a80  pop
0xf9a81  ldarg.0
0xf9a82  ldfld    class System.Web.UI.Design.WebControls.MenuDesigner MenuDesignerActionList::_parent
0xf9a87  callvirt instance bool System.Web.UI.Design.WebControls.MenuDesigner::get_StaticTemplated()
0xf9a8c  brfalse.s loc_F9AB8
0xf9a8e  ldloc.0
0xf9a8f  ldarg.0
0xf9a90  ldstr    aResetstatictem// "ResetStaticTemplate"
0xf9a95  ldstr    aMenudesignerRe_0// "MenuDesigner_ResetStaticTemplate"
0xf9a9a  call     string System.Design.SR::GetString(string name)
0xf9a9f  ldloc.1
0xf9aa0  ldstr    aMenudesignerRe_2// "MenuDesigner_ResetStaticTemplateDescrip"...
0xf9aa5  call     string System.Design.SR::GetString(string name)
0xf9aaa  ldc.i4.1
0xf9aab  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf9ab0  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf9ab5  pop
0xf9ab6  br.s     loc_F9AE0
0xf9ab8  ldloc.0
0xf9ab9  ldarg.0
0xf9aba  ldstr    aConverttostati// "ConvertToStaticTemplate"
0xf9abf  ldstr    aMenudesignerCo_0// "MenuDesigner_ConvertToStaticTemplate"
0xf9ac4  call     string System.Design.SR::GetString(string name)
0xf9ac9  ldloc.1
0xf9aca  ldstr    aMenudesignerCo_2// "MenuDesigner_ConvertToStaticTemplateDes"...
0xf9acf  call     string System.Design.SR::GetString(string name)
0xf9ad4  ldc.i4.1
0xf9ad5  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xf9ada  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xf9adf  pop
0xf9ae0  ldloc.0
0xf9ae1  ret
```
