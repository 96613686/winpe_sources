# TableLayouPanelRowColumnActionList::GetSortedActionItems

- ea: `0x121940`
- end: `0x1219ff`
- name: `TableLayouPanelRowColumnActionList::GetSortedActionItems`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x59920`
- `0x5d870`
- `0x5d8b0`
- `0x8ef40`
- `0xcadf0`
- `0x121940`

## string_xrefs

- `0x12199a`: `TableLayoutPanelDesignerRemoveColumn`
- `0x1219ca`: `TableLayoutPanelDesignerRemoveRow`
- `0x121995`: `RemoveColumn`
- `0x1219c5`: `RemoveRow`

## pseudocode

```c

```

## disassembly

```asm
0x121940  newobj   instance void System.ComponentModel.Design.DesignerActionItemCollection::.ctor()
0x121945  stloc.0
0x121946  ldloc.0
0x121947  ldarg.0
0x121948  ldstr    aAddcolumn// "AddColumn"
0x12194d  ldstr    aTablelayoutpan_11// "TableLayoutPanelDesignerAddColumn"
0x121952  call     string System.Design.SR::GetString(string name)
0x121957  ldc.i4.0
0x121958  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, bool includeAsDesignerVerb)
0x12195d  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x121962  pop
0x121963  ldloc.0
0x121964  ldarg.0
0x121965  ldstr    aAddrow// "AddRow"
0x12196a  ldstr    aTablelayoutpan_12// "TableLayoutPanelDesignerAddRow"
0x12196f  call     string System.Design.SR::GetString(string name)
0x121974  ldc.i4.0
0x121975  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, bool includeAsDesignerVerb)
0x12197a  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x12197f  pop
0x121980  ldarg.0
0x121981  ldfld    class System.Windows.Forms.Design.TableLayoutPanelDesigner TableLayouPanelRowColumnActionList::owner
0x121986  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0x12198b  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnCount()
0x121990  ldc.i4.1
0x121991  ble.s    loc_1219B0
0x121993  ldloc.0
0x121994  ldarg.0
0x121995  ldstr    aRemovecolumn// "RemoveColumn"
0x12199a  ldstr    aTablelayoutpan_9// "TableLayoutPanelDesignerRemoveColumn"
0x12199f  call     string System.Design.SR::GetString(string name)
0x1219a4  ldc.i4.0
0x1219a5  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, bool includeAsDesignerVerb)
0x1219aa  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x1219af  pop
0x1219b0  ldarg.0
0x1219b1  ldfld    class System.Windows.Forms.Design.TableLayoutPanelDesigner TableLayouPanelRowColumnActionList::owner
0x1219b6  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0x1219bb  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowCount()
0x1219c0  ldc.i4.1
0x1219c1  ble.s    loc_1219E0
0x1219c3  ldloc.0
0x1219c4  ldarg.0
0x1219c5  ldstr    aRemoverow// "RemoveRow"
0x1219ca  ldstr    aTablelayoutpan_10// "TableLayoutPanelDesignerRemoveRow"
0x1219cf  call     string System.Design.SR::GetString(string name)
0x1219d4  ldc.i4.0
0x1219d5  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, bool includeAsDesignerVerb)
0x1219da  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x1219df  pop
0x1219e0  ldloc.0
0x1219e1  ldarg.0
0x1219e2  ldstr    aEditrowandcol// "EditRowAndCol"
0x1219e7  ldstr    aTablelayoutpan_3// "TableLayoutPanelDesignerEditRowAndCol"
0x1219ec  call     string System.Design.SR::GetString(string name)
0x1219f1  ldc.i4.0
0x1219f2  newobj   instance void System.ComponentModel.Design.DesignerActionMethodItem::.ctor(class System.ComponentModel.Design.DesignerActionList actionList, string memberName, string displayName, bool includeAsDesignerVerb)
0x1219f7  callvirt instance int32 System.ComponentModel.Design.DesignerActionItemCollection::Add(class System.ComponentModel.Design.DesignerActionItem value)
0x1219fc  pop
0x1219fd  ldloc.0
0x1219fe  ret
```
