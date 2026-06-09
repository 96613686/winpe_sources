# TreeViewDesignerActionList::GetSortedActionItems

- ea: `0xff870`
- end: `0xff941`
- name: `TreeViewDesignerActionList::GetSortedActionItems`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x15380`
- `0x598e0`
- `0x5af90`
- `0x5d870`
- `0x5d8b0`
- `0x8ef40`
- `0xff7e0`
- `0xff870`

## string_xrefs

- `0xff8ef`: `CreateLineImages`
- `0xff8f4`: `TreeViewDesigner_CreateLineImages`
- `0xff8ff`: `TreeViewDesigner_CreateLineImagesDescription`

## pseudocode

```c

```

## disassembly

```asm
0xff870  newobj   instance void System.ComponentModel.Design.DesignerActionItemCollection::.ctor()
0xff875  stloc.0
0xff876  ldstr    aTreeviewdesign_5// "TreeViewDesigner_DataActionGroup"
0xff87b  call     string System.Design.SR::GetString(string name)
0xff880  stloc.1
0xff881  ldarg.0
0xff882  ldfld    class System.Web.UI.Design.WebControls.TreeViewDesigner TreeViewDesignerActionList::_parent
0xff887  callvirt instance string System.Web.UI.Design.WebControls.BaseDataBoundControlDesigner::get_DataSourceID()
0xff88c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xff891  brfalse.s loc_FF8BD
0xff893  ldloc.0
0xff894  ldarg.0
0xff895  ldstr    aEditnodes// "EditNodes"
0xff89a  ldstr    aTreeviewdesign_6// "TreeViewDesigner_EditNodes"
0xff89f  call     string System.Design.SR::GetString(string name)
0xff8a4  ldloc.1
0xff8a5  ldstr    aTreeviewdesign_7// "TreeViewDesigner_EditNodesDescription"
0xff8aa  call     string System.Design.SR::GetString(string name)
0xff8af  ldc.i4.1
0xff8b0  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xff8b5  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xff8ba  pop
0xff8bb  br.s     loc_FF8E5
0xff8bd  ldloc.0
0xff8be  ldarg.0
0xff8bf  ldstr    aEditbindings// "EditBindings"
0xff8c4  ldstr    aTreeviewdesign_8// "TreeViewDesigner_EditBindings"
0xff8c9  call     string System.Design.SR::GetString(string name)
0xff8ce  ldloc.1
0xff8cf  ldstr    aTreeviewdesign_9// "TreeViewDesigner_EditBindingsDescriptio"...
0xff8d4  call     string System.Design.SR::GetString(string name)
0xff8d9  ldc.i4.1
0xff8da  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xff8df  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xff8e4  pop
0xff8e5  ldarg.0
0xff8e6  call     instance bool TreeViewDesignerActionList::get_ShowLines()
0xff8eb  brfalse.s loc_FF915
0xff8ed  ldloc.0
0xff8ee  ldarg.0
0xff8ef  ldstr    aCreatelineimag// "CreateLineImages"
0xff8f4  ldstr    aTreeviewdesign_10// "TreeViewDesigner_CreateLineImages"
0xff8f9  call     string System.Design.SR::GetString(string name)
0xff8fe  ldloc.1
0xff8ff  ldstr    aTreeviewdesign_11// "TreeViewDesigner_CreateLineImagesDescri"...
0xff904  call     string System.Design.SR::GetString(string name)
0xff909  ldc.i4.1
0xff90a  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description, bool includeAsDesignerVerb)
0xff90f  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xff914  pop
0xff915  ldloc.0
0xff916  ldstr    aShowlines// "ShowLines"
0xff91b  ldstr    aTreeviewdesign_12// "TreeViewDesigner_ShowLines"
0xff920  call     string System.Design.SR::GetString(string name)
0xff925  ldstr    aActions// "Actions"
0xff92a  ldstr    aTreeviewdesign_13// "TreeViewDesigner_ShowLinesDescription"
0xff92f  call     string System.Design.SR::GetString(string name)
0xff934  newobj   instance void System.ComponentModel.Design.DesignerActionPropertyItem::.ctor(string memberName, string displayName, string category, string description)
0xff939  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0xff93e  pop
0xff93f  ldloc.0
0xff940  ret
```
