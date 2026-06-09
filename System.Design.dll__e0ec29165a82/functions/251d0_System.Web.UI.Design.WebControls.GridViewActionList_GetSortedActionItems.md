# System.Web.UI.Design.WebControls.GridViewActionList::GetSortedActionItems

- ea: `0x251d0`
- end: `0x253c1`
- name: `System.Web.UI.Design.WebControls.GridViewActionList::GetSortedActionItems`
- size: `497`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x24fc0`
- `0x24fe0`
- `0x25000`
- `0x25020`
- `0x25040`
- `0x25060`
- `0x25080`
- `0x250a0`
- `0x251d0`
- `0x59950`
- `0x5af90`
- `0x5d870`
- `0x5d8b0`
- `0x8ef40`

## string_xrefs

- `0x2529c`: `RemoveField`
- `0x25236`: `MoveFieldLeft`
- `0x2523b`: `GridView_MoveFieldLeftVerb`
- `0x2524a`: `GridView_MoveFieldLeftDesc`
- `0x25269`: `MoveFieldRight`
- `0x2526e`: `GridView_MoveFieldRightVerb`
- `0x2527d`: `GridView_MoveFieldRightDesc`
- `0x252a1`: `GridView_RemoveFieldVerb`
- `0x252b0`: `GridView_RemoveFieldDesc`

## pseudocode

```c

```

## disassembly

```asm
0x251d0  newobj   instance void System.ComponentModel.Design.DesignerActionItemCollection::.ctor()
0x251d5  stloc.0
0x251d6  ldloc.0
0x251d7  ldarg.0
0x251d8  ldstr    aEditfields// "EditFields"
0x251dd  ldstr    aGridviewEditfi_0// "GridView_EditFieldsVerb"
0x251e2  call     string System.Design.SR::GetString(string name)
0x251e7  ldstr    aAction// "Action"
0x251ec  ldstr    aGridviewEditfi_1// "GridView_EditFieldsDesc"
0x251f1  call     string System.Design.SR::GetString(string name)
0x251f6  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description)
0x251fb  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x25200  pop
0x25201  ldloc.0
0x25202  ldarg.0
0x25203  ldstr    aAddnewfield// "AddNewField"
0x25208  ldstr    aGridviewAddnew// "GridView_AddNewFieldVerb"
0x2520d  call     string System.Design.SR::GetString(string name)
0x25212  ldstr    aAction// "Action"
0x25217  ldstr    aGridviewAddnew_0// "GridView_AddNewFieldDesc"
0x2521c  call     string System.Design.SR::GetString(string name)
0x25221  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description)
0x25226  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x2522b  pop
0x2522c  ldarg.0
0x2522d  call     instance bool System.Web.UI.Design.WebControls.GridViewActionList::get_AllowMoveLeft()
0x25232  brfalse.s loc_2525F
0x25234  ldloc.0
0x25235  ldarg.0
0x25236  ldstr    aMovefieldleft// "MoveFieldLeft"
0x2523b  ldstr    aGridviewMovefi// "GridView_MoveFieldLeftVerb"
0x25240  call     string System.Design.SR::GetString(string name)
0x25245  ldstr    aAction// "Action"
0x2524a  ldstr    aGridviewMovefi_0// "GridView_MoveFieldLeftDesc"
0x2524f  call     string System.Design.SR::GetString(string name)
0x25254  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description)
0x25259  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x2525e  pop
0x2525f  ldarg.0
0x25260  call     instance bool System.Web.UI.Design.WebControls.GridViewActionList::get_AllowMoveRight()
0x25265  brfalse.s loc_25292
0x25267  ldloc.0
0x25268  ldarg.0
0x25269  ldstr    aMovefieldright// "MoveFieldRight"
0x2526e  ldstr    aGridviewMovefi_1// "GridView_MoveFieldRightVerb"
0x25273  call     string System.Design.SR::GetString(string name)
0x25278  ldstr    aAction// "Action"
0x2527d  ldstr    aGridviewMovefi_2// "GridView_MoveFieldRightDesc"
0x25282  call     string System.Design.SR::GetString(string name)
0x25287  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description)
0x2528c  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x25291  pop
0x25292  ldarg.0
0x25293  call     instance bool System.Web.UI.Design.WebControls.GridViewActionList::get_AllowRemoveField()
0x25298  brfalse.s loc_252C5
0x2529a  ldloc.0
0x2529b  ldarg.0
0x2529c  ldstr    aRemovefield// "RemoveField"
0x252a1  ldstr    aGridviewRemove// "GridView_RemoveFieldVerb"
0x252a6  call     string System.Design.SR::GetString(string name)
0x252ab  ldstr    aAction// "Action"
0x252b0  ldstr    aGridviewRemove_0// "GridView_RemoveFieldDesc"
0x252b5  call     string System.Design.SR::GetString(string name)
0x252ba  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description)
0x252bf  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x252c4  pop
0x252c5  ldarg.0
0x252c6  call     instance bool System.Web.UI.Design.WebControls.GridViewActionList::get_AllowPaging()
0x252cb  brfalse.s loc_252F7
0x252cd  ldloc.0
0x252ce  ldstr    aEnablepaging// "EnablePaging"
0x252d3  ldstr    aGridviewEnable// "GridView_EnablePaging"
0x252d8  call     string System.Design.SR::GetString(string name)
0x252dd  ldstr    aBehavior// "Behavior"
0x252e2  ldstr    aGridviewEnable_0// "GridView_EnablePagingDesc"
0x252e7  call     string System.Design.SR::GetString(string name)
0x252ec  newobj   instance void System.ComponentModel.Design.DesignerActionPropertyItem::.ctor(string memberName, string displayName, string category, string description)
0x252f1  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x252f6  pop
0x252f7  ldarg.0
0x252f8  call     instance bool System.Web.UI.Design.WebControls.GridViewActionList::get_AllowSorting()
0x252fd  brfalse.s loc_25329
0x252ff  ldloc.0
0x25300  ldstr    aEnablesorting// "EnableSorting"
0x25305  ldstr    aGridviewEnable_1// "GridView_EnableSorting"
0x2530a  call     string System.Design.SR::GetString(string name)
0x2530f  ldstr    aBehavior// "Behavior"
0x25314  ldstr    aGridviewEnable_2// "GridView_EnableSortingDesc"
0x25319  call     string System.Design.SR::GetString(string name)
0x2531e  newobj   instance void System.ComponentModel.Design.DesignerActionPropertyItem::.ctor(string memberName, string displayName, string category, string description)
0x25323  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x25328  pop
0x25329  ldarg.0
0x2532a  call     instance bool System.Web.UI.Design.WebControls.GridViewActionList::get_AllowEditing()
0x2532f  brfalse.s loc_2535B
0x25331  ldloc.0
0x25332  ldstr    aEnableediting// "EnableEditing"
0x25337  ldstr    aGridviewEnable_3// "GridView_EnableEditing"
0x2533c  call     string System.Design.SR::GetString(string name)
0x25341  ldstr    aBehavior// "Behavior"
0x25346  ldstr    aGridviewEnable_4// "GridView_EnableEditingDesc"
0x2534b  call     string System.Design.SR::GetString(string name)
0x25350  newobj   instance void System.ComponentModel.Design.DesignerActionPropertyItem::.ctor(string memberName, string displayName, string category, string description)
0x25355  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x2535a  pop
0x2535b  ldarg.0
0x2535c  call     instance bool System.Web.UI.Design.WebControls.GridViewActionList::get_AllowDeleting()
0x25361  brfalse.s loc_2538D
0x25363  ldloc.0
0x25364  ldstr    aEnabledeleting// "EnableDeleting"
0x25369  ldstr    aGridviewEnable_5// "GridView_EnableDeleting"
0x2536e  call     string System.Design.SR::GetString(string name)
0x25373  ldstr    aBehavior// "Behavior"
0x25378  ldstr    aGridviewEnable_6// "GridView_EnableDeletingDesc"
0x2537d  call     string System.Design.SR::GetString(string name)
0x25382  newobj   instance void System.ComponentModel.Design.DesignerActionPropertyItem::.ctor(string memberName, string displayName, string category, string description)
0x25387  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x2538c  pop
0x2538d  ldarg.0
0x2538e  call     instance bool System.Web.UI.Design.WebControls.GridViewActionList::get_AllowSelection()
0x25393  brfalse.s loc_253BF
0x25395  ldloc.0
0x25396  ldstr    aEnableselectio// "EnableSelection"
0x2539b  ldstr    aGridviewEnable_7// "GridView_EnableSelection"
0x253a0  call     string System.Design.SR::GetString(string name)
0x253a5  ldstr    aBehavior// "Behavior"
0x253aa  ldstr    aGridviewEnable_8// "GridView_EnableSelectionDesc"
0x253af  call     string System.Design.SR::GetString(string name)
0x253b4  newobj   instance void System.ComponentModel.Design.DesignerActionPropertyItem::.ctor(string memberName, string displayName, string category, string description)
0x253b9  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x253be  pop
0x253bf  ldloc.0
0x253c0  ret
```
