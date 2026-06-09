# System.Web.UI.Design.WebControls.DetailsViewActionList::GetSortedActionItems

- ea: `0x21840`
- end: `0x219ff`
- name: `System.Web.UI.Design.WebControls.DetailsViewActionList::GetSortedActionItems`
- size: `447`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x21670`
- `0x21690`
- `0x216b0`
- `0x216d0`
- `0x216f0`
- `0x21710`
- `0x21730`
- `0x21840`
- `0x59950`
- `0x5af90`
- `0x5d870`
- `0x5d8b0`
- `0x8ef40`

## string_xrefs

- `0x218a6`: `MoveFieldUp`
- `0x218ab`: `DetailsView_MoveFieldUpVerb`
- `0x218ba`: `DetailsView_MoveFieldUpDesc`
- `0x218d9`: `MoveFieldDown`
- `0x218de`: `DetailsView_MoveFieldDownVerb`
- `0x218ed`: `DetailsView_MoveFieldDownDesc`
- `0x2190c`: `RemoveField`
- `0x21911`: `DetailsView_RemoveFieldVerb`
- `0x21920`: `DetailsView_RemoveFieldDesc`

## pseudocode

```c

```

## disassembly

```asm
0x21840  newobj   instance void System.ComponentModel.Design.DesignerActionItemCollection::.ctor()
0x21845  stloc.0
0x21846  ldloc.0
0x21847  ldarg.0
0x21848  ldstr    aEditfields// "EditFields"
0x2184d  ldstr    aDetailsviewEdi// "DetailsView_EditFieldsVerb"
0x21852  call     string System.Design.SR::GetString(string name)
0x21857  ldstr    aAction// "Action"
0x2185c  ldstr    aDetailsviewEdi_0// "DetailsView_EditFieldsDesc"
0x21861  call     string System.Design.SR::GetString(string name)
0x21866  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description)
0x2186b  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x21870  pop
0x21871  ldloc.0
0x21872  ldarg.0
0x21873  ldstr    aAddnewfield// "AddNewField"
0x21878  ldstr    aDetailsviewAdd// "DetailsView_AddNewFieldVerb"
0x2187d  call     string System.Design.SR::GetString(string name)
0x21882  ldstr    aAction// "Action"
0x21887  ldstr    aDetailsviewAdd_0// "DetailsView_AddNewFieldDesc"
0x2188c  call     string System.Design.SR::GetString(string name)
0x21891  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description)
0x21896  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x2189b  pop
0x2189c  ldarg.0
0x2189d  call     instance bool System.Web.UI.Design.WebControls.DetailsViewActionList::get_AllowMoveUp()
0x218a2  brfalse.s loc_218CF
0x218a4  ldloc.0
0x218a5  ldarg.0
0x218a6  ldstr    aMovefieldup// "MoveFieldUp"
0x218ab  ldstr    aDetailsviewMov// "DetailsView_MoveFieldUpVerb"
0x218b0  call     string System.Design.SR::GetString(string name)
0x218b5  ldstr    aAction// "Action"
0x218ba  ldstr    aDetailsviewMov_0// "DetailsView_MoveFieldUpDesc"
0x218bf  call     string System.Design.SR::GetString(string name)
0x218c4  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description)
0x218c9  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x218ce  pop
0x218cf  ldarg.0
0x218d0  call     instance bool System.Web.UI.Design.WebControls.DetailsViewActionList::get_AllowMoveDown()
0x218d5  brfalse.s loc_21902
0x218d7  ldloc.0
0x218d8  ldarg.0
0x218d9  ldstr    aMovefielddown// "MoveFieldDown"
0x218de  ldstr    aDetailsviewMov_1// "DetailsView_MoveFieldDownVerb"
0x218e3  call     string System.Design.SR::GetString(string name)
0x218e8  ldstr    aAction// "Action"
0x218ed  ldstr    aDetailsviewMov_2// "DetailsView_MoveFieldDownDesc"
0x218f2  call     string System.Design.SR::GetString(string name)
0x218f7  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description)
0x218fc  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x21901  pop
0x21902  ldarg.0
0x21903  call     instance bool System.Web.UI.Design.WebControls.DetailsViewActionList::get_AllowRemoveField()
0x21908  brfalse.s loc_21935
0x2190a  ldloc.0
0x2190b  ldarg.0
0x2190c  ldstr    aRemovefield// "RemoveField"
0x21911  ldstr    aDetailsviewRem// "DetailsView_RemoveFieldVerb"
0x21916  call     string System.Design.SR::GetString(string name)
0x2191b  ldstr    aAction// "Action"
0x21920  ldstr    aDetailsviewRem_0// "DetailsView_RemoveFieldDesc"
0x21925  call     string System.Design.SR::GetString(string name)
0x2192a  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, string category, string description)
0x2192f  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x21934  pop
0x21935  ldarg.0
0x21936  call     instance bool System.Web.UI.Design.WebControls.DetailsViewActionList::get_AllowPaging()
0x2193b  brfalse.s loc_21967
0x2193d  ldloc.0
0x2193e  ldstr    aEnablepaging// "EnablePaging"
0x21943  ldstr    aDetailsviewEna// "DetailsView_EnablePaging"
0x21948  call     string System.Design.SR::GetString(string name)
0x2194d  ldstr    aBehavior// "Behavior"
0x21952  ldstr    aDetailsviewEna_0// "DetailsView_EnablePagingDesc"
0x21957  call     string System.Design.SR::GetString(string name)
0x2195c  newobj   instance void System.ComponentModel.Design.DesignerActionPropertyItem::.ctor(string memberName, string displayName, string category, string description)
0x21961  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x21966  pop
0x21967  ldarg.0
0x21968  call     instance bool System.Web.UI.Design.WebControls.DetailsViewActionList::get_AllowInserting()
0x2196d  brfalse.s loc_21999
0x2196f  ldloc.0
0x21970  ldstr    aEnableinsertin// "EnableInserting"
0x21975  ldstr    aDetailsviewEna_1// "DetailsView_EnableInserting"
0x2197a  call     string System.Design.SR::GetString(string name)
0x2197f  ldstr    aBehavior// "Behavior"
0x21984  ldstr    aDetailsviewEna_2// "DetailsView_EnableInsertingDesc"
0x21989  call     string System.Design.SR::GetString(string name)
0x2198e  newobj   instance void System.ComponentModel.Design.DesignerActionPropertyItem::.ctor(string memberName, string displayName, string category, string description)
0x21993  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x21998  pop
0x21999  ldarg.0
0x2199a  call     instance bool System.Web.UI.Design.WebControls.DetailsViewActionList::get_AllowEditing()
0x2199f  brfalse.s loc_219CB
0x219a1  ldloc.0
0x219a2  ldstr    aEnableediting// "EnableEditing"
0x219a7  ldstr    aDetailsviewEna_3// "DetailsView_EnableEditing"
0x219ac  call     string System.Design.SR::GetString(string name)
0x219b1  ldstr    aBehavior// "Behavior"
0x219b6  ldstr    aDetailsviewEna_4// "DetailsView_EnableEditingDesc"
0x219bb  call     string System.Design.SR::GetString(string name)
0x219c0  newobj   instance void System.ComponentModel.Design.DesignerActionPropertyItem::.ctor(string memberName, string displayName, string category, string description)
0x219c5  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x219ca  pop
0x219cb  ldarg.0
0x219cc  call     instance bool System.Web.UI.Design.WebControls.DetailsViewActionList::get_AllowDeleting()
0x219d1  brfalse.s loc_219FD
0x219d3  ldloc.0
0x219d4  ldstr    aEnabledeleting// "EnableDeleting"
0x219d9  ldstr    aDetailsviewEna_5// "DetailsView_EnableDeleting"
0x219de  call     string System.Design.SR::GetString(string name)
0x219e3  ldstr    aBehavior// "Behavior"
0x219e8  ldstr    aDetailsviewEna_6// "DetailsView_EnableDeletingDesc"
0x219ed  call     string System.Design.SR::GetString(string name)
0x219f2  newobj   instance void System.ComponentModel.Design.DesignerActionPropertyItem::.ctor(string memberName, string displayName, string category, string description)
0x219f7  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x219fc  pop
0x219fd  ldloc.0
0x219fe  ret
```
