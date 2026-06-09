# System.Windows.Forms.Design.TableLayoutPanelDesigner::get_DesignerContextMenuStrip

- ea: `0xcab50`
- end: `0xcadba`
- name: `System.Windows.Forms.Design.TableLayoutPanelDesigner::get_DesignerContextMenuStrip`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0xcc640`

## callees

- `0x584f0`
- `0x58710`
- `0x8ef40`
- `0x94e90`
- `0x9fc00`
- `0x9fc40`
- `0xb9b60`
- `0xcab50`
- `0xcadf0`
- `0xcb060`
- `0xcc590`

## string_xrefs

- `0xcad2a`: `ContextMenuCopy`
- `0xcad55`: `ContextMenuDelete`
- `0xcad3d`: `TableLayoutPanelDesignerContextMenuCopy`
- `0xcad68`: `TableLayoutPanelDesignerContextMenuDelete`

## pseudocode

```c

```

## disassembly

```asm
0xcab50  ldarg.0
0xcab51  ldfld    class System.Windows.Forms.Design.BaseContextMenuStrip System.Windows.Forms.Design.TableLayoutPanelDesigner::designerContextMenuStrip
0xcab56  brtrue   loc_CAD93
0xcab5b  ldarg.0
0xcab5c  ldarg.0
0xcab5d  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0xcab62  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0xcab67  ldarg.0
0xcab68  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcab6d  newobj   instance void System.Windows.Forms.Design.BaseContextMenuStrip::.ctor(class [mscorlib]System.IServiceProvider provider, class [System]System.ComponentModel.Component component)
0xcab72  stfld    class System.Windows.Forms.Design.BaseContextMenuStrip System.Windows.Forms.Design.TableLayoutPanelDesigner::designerContextMenuStrip
0xcab77  ldarg.0
0xcab78  ldfld    class System.Windows.Forms.Design.BaseContextMenuStrip System.Windows.Forms.Design.TableLayoutPanelDesigner::designerContextMenuStrip
0xcab7d  callvirt instance class System.Windows.Forms.Design.ContextMenuStripGroupCollection System.Windows.Forms.Design.GroupedContextMenuStrip::get_Groups()
0xcab82  ldstr    aVerbs// "Verbs"
0xcab87  callvirt instance class System.Windows.Forms.Design.ContextMenuStripGroup System.Windows.Forms.Design.ContextMenuStripGroupCollection::get_Item(string key)
0xcab8c  stloc.1
0xcab8d  ldarg.0
0xcab8e  callvirt instance class [System]System.ComponentModel.Design.DesignerVerbCollection System.ComponentModel.Design.ComponentDesigner::get_Verbs()
0xcab93  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xcab98  stloc.s  4
0xcab9a  br.s     loc_CAC18
0xcab9c  ldloc.s  4
0xcab9e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xcaba3  castclass [System]System.ComponentModel.Design.DesignerVerb
0xcaba8  stloc.s  5
0xcabaa  ldloc.s  5
0xcabac  callvirt instance string [System]System.ComponentModel.Design.DesignerVerb::get_Text()
0xcabb1  ldstr    aTablelayoutpan_3// "TableLayoutPanelDesignerEditRowAndCol"
0xcabb6  call     string System.Design.SR::GetString(string name)
0xcabbb  callvirt instance bool [mscorlib]System.String::Equals(string)
0xcabc0  brtrue.s loc_CAC18
0xcabc2  ldloc.1
0xcabc3  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem> System.Windows.Forms.Design.ContextMenuStripGroup::get_Items()
0xcabc8  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem>::GetEnumerator()
0xcabcd  stloc.s  6
0xcabcf  br.s     loc_CABFF
0xcabd1  ldloca.s 6
0xcabd3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem>::get_Current()
0xcabd8  stloc.s  7
0xcabda  ldloc.s  7
0xcabdc  callvirt instance string [System.Windows.Forms]System.Windows.Forms.ToolStripItem::get_Text()
0xcabe1  ldloc.s  5
0xcabe3  callvirt instance string [System]System.ComponentModel.Design.DesignerVerb::get_Text()
0xcabe8  callvirt instance bool [mscorlib]System.String::Equals(string)
0xcabed  brfalse.s loc_CABFF
0xcabef  ldloc.1
0xcabf0  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem> System.Windows.Forms.Design.ContextMenuStripGroup::get_Items()
0xcabf5  ldloc.s  7
0xcabf7  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem>::Remove(var<u1>)
0xcabfc  pop
0xcabfd  leave.s  loc_CAC18
0xcabff  ldloca.s 6
0xcac01  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem>::MoveNext()
0xcac06  brtrue.s loc_CABD1
0xcac08  leave.s  loc_CAC18
0xcac0a  ldloca.s 6
0xcac0c  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem>
0xcac12  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcac17  endfinally
0xcac18  ldloc.s  4
0xcac1a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xcac1f  brtrue   loc_CAB9C
0xcac24  leave.s  loc_CAC3B
0xcac26  ldloc.s  4
0xcac28  isinst   [mscorlib]System.IDisposable
0xcac2d  stloc.s  8
0xcac2f  ldloc.s  8
0xcac31  brfalse.s loc_CAC3A
0xcac33  ldloc.s  8
0xcac35  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcac3a  endfinally
0xcac3b  ldarg.0
0xcac3c  ldc.i4.1
0xcac3d  call     instance class [System.Windows.Forms]System.Windows.Forms.ToolStripDropDownMenu System.Windows.Forms.Design.TableLayoutPanelDesigner::BuildMenu(bool isRow)
0xcac42  stloc.2
0xcac43  ldarg.0
0xcac44  ldc.i4.0
0xcac45  call     instance class [System.Windows.Forms]System.Windows.Forms.ToolStripDropDownMenu System.Windows.Forms.Design.TableLayoutPanelDesigner::BuildMenu(bool isRow)
0xcac4a  stloc.3
0xcac4b  ldarg.0
0xcac4c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem::.ctor()
0xcac51  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem System.Windows.Forms.Design.TableLayoutPanelDesigner::contextMenuRow
0xcac56  ldarg.0
0xcac57  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem System.Windows.Forms.Design.TableLayoutPanelDesigner::contextMenuRow
0xcac5c  ldloc.2
0xcac5d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripDropDownItem::set_DropDown(class [System.Windows.Forms]System.Windows.Forms.ToolStripDropDown)
0xcac62  ldarg.0
0xcac63  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem System.Windows.Forms.Design.TableLayoutPanelDesigner::contextMenuRow
0xcac68  ldstr    aTablelayoutpan_4// "TableLayoutPanelDesignerRowMenu"
0xcac6d  call     string System.Design.SR::GetString(string name)
0xcac72  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Text(string)
0xcac77  ldarg.0
0xcac78  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem::.ctor()
0xcac7d  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem System.Windows.Forms.Design.TableLayoutPanelDesigner::contextMenuCol
0xcac82  ldarg.0
0xcac83  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem System.Windows.Forms.Design.TableLayoutPanelDesigner::contextMenuCol
0xcac88  ldloc.3
0xcac89  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripDropDownItem::set_DropDown(class [System.Windows.Forms]System.Windows.Forms.ToolStripDropDown)
0xcac8e  ldarg.0
0xcac8f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem System.Windows.Forms.Design.TableLayoutPanelDesigner::contextMenuCol
0xcac94  ldstr    aTablelayoutpan_5// "TableLayoutPanelDesignerColMenu"
0xcac99  call     string System.Design.SR::GetString(string name)
0xcac9e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Text(string)
0xcaca3  ldloc.1
0xcaca4  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem> System.Windows.Forms.Design.ContextMenuStripGroup::get_Items()
0xcaca9  ldc.i4.0
0xcacaa  ldarg.0
0xcacab  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem System.Windows.Forms.Design.TableLayoutPanelDesigner::contextMenuCol
0xcacb0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem>::Insert(int32, var<u1>)
0xcacb5  ldloc.1
0xcacb6  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem> System.Windows.Forms.Design.ContextMenuStripGroup::get_Items()
0xcacbb  ldc.i4.0
0xcacbc  ldarg.0
0xcacbd  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem System.Windows.Forms.Design.TableLayoutPanelDesigner::contextMenuRow
0xcacc2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem>::Insert(int32, var<u1>)
0xcacc7  ldarg.0
0xcacc8  ldfld    class System.Windows.Forms.Design.BaseContextMenuStrip System.Windows.Forms.Design.TableLayoutPanelDesigner::designerContextMenuStrip
0xcaccd  callvirt instance class System.Windows.Forms.Design.ContextMenuStripGroupCollection System.Windows.Forms.Design.GroupedContextMenuStrip::get_Groups()
0xcacd2  ldstr    aEdit// "Edit"
0xcacd7  callvirt instance class System.Windows.Forms.Design.ContextMenuStripGroup System.Windows.Forms.Design.ContextMenuStripGroupCollection::get_Item(string key)
0xcacdc  stloc.1
0xcacdd  ldloc.1
0xcacde  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem> System.Windows.Forms.Design.ContextMenuStripGroup::get_Items()
0xcace3  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem>::GetEnumerator()
0xcace8  stloc.s  9
0xcacea  br       loc_CAD77
0xcacef  ldloca.s 9
0xcacf1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem>::get_Current()
0xcacf6  stloc.s  0xA
0xcacf8  ldloc.s  0xA
0xcacfa  callvirt instance string [System.Windows.Forms]System.Windows.Forms.ToolStripItem::get_Text()
0xcacff  ldstr    aContextmenucut// "ContextMenuCut"
0xcad04  call     string System.Design.SR::GetString(string name)
0xcad09  callvirt instance bool [mscorlib]System.String::Equals(string)
0xcad0e  brfalse.s loc_CAD23
0xcad10  ldloc.s  0xA
0xcad12  ldstr    aTablelayoutpan_6// "TableLayoutPanelDesignerContextMenuCut"
0xcad17  call     string System.Design.SR::GetString(string name)
0xcad1c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Text(string)
0xcad21  br.s     loc_CAD77
0xcad23  ldloc.s  0xA
0xcad25  callvirt instance string [System.Windows.Forms]System.Windows.Forms.ToolStripItem::get_Text()
0xcad2a  ldstr    aContextmenucop// "ContextMenuCopy"
0xcad2f  call     string System.Design.SR::GetString(string name)
0xcad34  callvirt instance bool [mscorlib]System.String::Equals(string)
0xcad39  brfalse.s loc_CAD4E
0xcad3b  ldloc.s  0xA
0xcad3d  ldstr    aTablelayoutpan_7// "TableLayoutPanelDesignerContextMenuCopy"
0xcad42  call     string System.Design.SR::GetString(string name)
0xcad47  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Text(string)
0xcad4c  br.s     loc_CAD77
0xcad4e  ldloc.s  0xA
0xcad50  callvirt instance string [System.Windows.Forms]System.Windows.Forms.ToolStripItem::get_Text()
0xcad55  ldstr    aContextmenudel// "ContextMenuDelete"
0xcad5a  call     string System.Design.SR::GetString(string name)
0xcad5f  callvirt instance bool [mscorlib]System.String::Equals(string)
0xcad64  brfalse.s loc_CAD77
0xcad66  ldloc.s  0xA
0xcad68  ldstr    aTablelayoutpan_8// "TableLayoutPanelDesignerContextMenuDele"...
0xcad6d  call     string System.Design.SR::GetString(string name)
0xcad72  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Text(string)
0xcad77  ldloca.s 9
0xcad79  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem>::MoveNext()
0xcad7e  brtrue   loc_CACEF
0xcad83  leave.s  loc_CAD93
0xcad85  ldloca.s 9
0xcad87  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System.Windows.Forms]System.Windows.Forms.ToolStripItem>
0xcad8d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcad92  endfinally
0xcad93  ldarg.0
0xcad94  ldc.i4.0
0xcad95  call     instance bool System.Windows.Forms.Design.TableLayoutPanelDesigner::IsOverValidCell(bool dragOp)
0xcad9a  stloc.0
0xcad9b  ldarg.0
0xcad9c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem System.Windows.Forms.Design.TableLayoutPanelDesigner::contextMenuRow
0xcada1  ldloc.0
0xcada2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Enabled(bool)
0xcada7  ldarg.0
0xcada8  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem System.Windows.Forms.Design.TableLayoutPanelDesigner::contextMenuCol
0xcadad  ldloc.0
0xcadae  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Enabled(bool)
0xcadb3  ldarg.0
0xcadb4  ldfld    class System.Windows.Forms.Design.BaseContextMenuStrip System.Windows.Forms.Design.TableLayoutPanelDesigner::designerContextMenuStrip
0xcadb9  ret
```
