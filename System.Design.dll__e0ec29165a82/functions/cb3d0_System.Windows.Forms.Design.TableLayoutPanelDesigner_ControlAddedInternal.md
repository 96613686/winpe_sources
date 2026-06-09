# System.Windows.Forms.Design.TableLayoutPanelDesigner::ControlAddedInternal

- ea: `0xcb3d0`
- end: `0xcb753`
- name: `System.Windows.Forms.Design.TableLayoutPanelDesigner::ControlAddedInternal`
- size: `899`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `service_task`

## callers

- `0xcc490`
- `0xcc6e0`

## callees

- `0x584f0`
- `0x58ca0`
- `0x8eec0`
- `0x8efb0`
- `0xa27e0`
- `0xb2d20`
- `0xc2d30`
- `0xcadf0`
- `0xcb340`
- `0xcb380`
- `0xcb3d0`
- `0xcc010`
- `0xcdb40`
- `0xcdb60`

## string_xrefs

- `0xcb5d7`: `BehaviorServiceMoveControl`
- `0xcb509`: `BehaviorServiceCopyControl`

## pseudocode

```c

```

## disassembly

```asm
0xcb3d0  ldarg.s  4
0xcb3d2  brfalse  loc_CB49B
0xcb3d7  ldarg.0
0xcb3d8  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcb3dd  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.TableLayoutPanelGrowStyle [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_GrowStyle()
0xcb3e2  ldc.i4.1
0xcb3e3  bne.un.s loc_CB43A
0xcb3e5  ldarg.0
0xcb3e6  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcb3eb  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xcb3f0  ldstr    aRowcount// "RowCount"
0xcb3f5  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xcb3fa  stloc.2
0xcb3fb  ldloc.2
0xcb3fc  brfalse.s loc_CB41C
0xcb3fe  ldloc.2
0xcb3ff  ldarg.0
0xcb400  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcb405  ldarg.0
0xcb406  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcb40b  callvirt instance int32[] [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::GetRowHeights()
0xcb410  ldlen
0xcb411  conv.i4
0xcb412  box      [mscorlib]System.Int32
0xcb417  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0xcb41c  ldarga.s 2
0xcb41e  ldc.i4.0
0xcb41f  call     instance void [System.Drawing]System.Drawing.Point::set_X(int32)
0xcb424  ldarga.s 2
0xcb426  ldarg.0
0xcb427  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcb42c  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowCount()
0xcb431  ldc.i4.1
0xcb432  sub
0xcb433  call     instance void [System.Drawing]System.Drawing.Point::set_Y(int32)
0xcb438  br.s     loc_CB49B
0xcb43a  ldarg.0
0xcb43b  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcb440  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.TableLayoutPanelGrowStyle [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_GrowStyle()
0xcb445  ldc.i4.2
0xcb446  bne.un.s loc_CB49B
0xcb448  ldarg.0
0xcb449  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcb44e  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xcb453  ldstr    aColumncount// "ColumnCount"
0xcb458  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xcb45d  stloc.3
0xcb45e  ldloc.3
0xcb45f  brfalse.s loc_CB47F
0xcb461  ldloc.3
0xcb462  ldarg.0
0xcb463  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcb468  ldarg.0
0xcb469  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcb46e  callvirt instance int32[] [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::GetColumnWidths()
0xcb473  ldlen
0xcb474  conv.i4
0xcb475  box      [mscorlib]System.Int32
0xcb47a  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0xcb47f  ldarga.s 2
0xcb481  ldarg.0
0xcb482  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcb487  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnCount()
0xcb48c  ldc.i4.1
0xcb48d  sub
0xcb48e  call     instance void [System.Drawing]System.Drawing.Point::set_X(int32)
0xcb493  ldarga.s 2
0xcb495  ldc.i4.0
0xcb496  call     instance void [System.Drawing]System.Drawing.Point::set_Y(int32)
0xcb49b  ldnull
0xcb49c  stloc.0
0xcb49d  ldarg.0
0xcb49e  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcb4a3  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xcb4a8  ldstr    aControls// "Controls"
0xcb4ad  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xcb4b2  stloc.1
0xcb4b3  ldarg.s  5
0xcb4b5  brfalse.s loc_CB4C3
0xcb4b7  ldarg.s  5
0xcb4b9  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DragDropEffects [System.Windows.Forms]System.Windows.Forms.DragEventArgs::get_Effect()
0xcb4be  ldc.i4.1
0xcb4bf  ceq
0xcb4c1  br.s     loc_CB4C4
0xcb4c3  ldc.i4.0
0xcb4c4  ldarg.3
0xcb4c5  and
0xcb4c6  stloc.s  4
0xcb4c8  ldarg.0
0xcb4c9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control System.Windows.Forms.Design.ControlDesigner::get_Control()
0xcb4ce  castclass [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel
0xcb4d3  ldarga.s 2
0xcb4d5  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0xcb4da  ldarga.s 2
0xcb4dc  call     instance int32 [System.Drawing]System.Drawing.Point::get_Y()
0xcb4e1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::GetControlFromPosition(int32, int32)
0xcb4e6  stloc.s  5
0xcb4e8  ldloc.s  4
0xcb4ea  brfalse.s loc_CB539
0xcb4ec  ldarg.0
0xcb4ed  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0xcb4f2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xcb4f7  callvirt instance object System.ComponentModel.Design.ComponentDesigner::GetService(class [mscorlib]System.Type serviceType)
0xcb4fc  isinst   [System]System.ComponentModel.Design.IDesignerHost
0xcb501  stloc.s  6
0xcb503  ldloc.s  6
0xcb505  brfalse.s loc_CB52D
0xcb507  ldloc.s  6
0xcb509  ldstr    aBehaviorservic_0// "BehaviorServiceCopyControl"
0xcb50e  ldc.i4.1
0xcb50f  newarr   [mscorlib]System.Object
0xcb514  dup
0xcb515  ldc.i4.0
0xcb516  ldarg.1
0xcb517  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.Component::get_Site()
0xcb51c  callvirt instance string [System]System.ComponentModel.ISite::get_Name()
0xcb521  stelem.ref
0xcb522  call     string System.Design.SR::GetString(string name, object[] args)
0xcb527  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0xcb52c  stloc.0
0xcb52d  ldarg.0
0xcb52e  ldloc.1
0xcb52f  call     instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::PropChanging(class [System]System.ComponentModel.PropertyDescriptor prop)
0xcb534  br       loc_CB605
0xcb539  ldloc.s  5
0xcb53b  brfalse.s loc_CB5B7
0xcb53d  ldloc.s  5
0xcb53f  ldarg.1
0xcb540  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xcb545  brtrue.s loc_CB5B7
0xcb547  ldarg.3
0xcb548  brfalse.s loc_CB5AB
0xcb54a  ldarg.0
0xcb54b  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0xcb550  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xcb555  callvirt instance object System.ComponentModel.Design.ComponentDesigner::GetService(class [mscorlib]System.Type serviceType)
0xcb55a  isinst   [System]System.ComponentModel.Design.IDesignerHost
0xcb55f  stloc.s  7
0xcb561  ldloc.s  7
0xcb563  brfalse.s loc_CB59A
0xcb565  ldloc.s  7
0xcb567  ldstr    aTablelayoutpan_21// "TableLayoutPanelDesignerControlsSwapped"
0xcb56c  ldc.i4.2
0xcb56d  newarr   [mscorlib]System.Object
0xcb572  dup
0xcb573  ldc.i4.0
0xcb574  ldarg.1
0xcb575  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.Component::get_Site()
0xcb57a  callvirt instance string [System]System.ComponentModel.ISite::get_Name()
0xcb57f  stelem.ref
0xcb580  dup
0xcb581  ldc.i4.1
0xcb582  ldloc.s  5
0xcb584  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.Component::get_Site()
0xcb589  callvirt instance string [System]System.ComponentModel.ISite::get_Name()
0xcb58e  stelem.ref
0xcb58f  call     string System.Design.SR::GetString(string name, object[] args)
0xcb594  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0xcb599  stloc.0
0xcb59a  ldarg.0
0xcb59b  ldloc.1
0xcb59c  call     instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::PropChanging(class [System]System.ComponentModel.PropertyDescriptor prop)
0xcb5a1  ldarg.0
0xcb5a2  ldloc.s  5
0xcb5a4  call     instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::RemoveControlInternal(class [System.Windows.Forms]System.Windows.Forms.Control c)
0xcb5a9  br.s     loc_CB605
0xcb5ab  ldarg.0
0xcb5ac  ldloc.1
0xcb5ad  call     instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::PropChanging(class [System]System.ComponentModel.PropertyDescriptor prop)
0xcb5b2  ldnull
0xcb5b3  stloc.s  5
0xcb5b5  br.s     loc_CB605
0xcb5b7  ldarg.3
0xcb5b8  brfalse.s loc_CB5FB
0xcb5ba  ldarg.0
0xcb5bb  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0xcb5c0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xcb5c5  callvirt instance object System.ComponentModel.Design.ComponentDesigner::GetService(class [mscorlib]System.Type serviceType)
0xcb5ca  isinst   [System]System.ComponentModel.Design.IDesignerHost
0xcb5cf  stloc.s  8
0xcb5d1  ldloc.s  8
0xcb5d3  brfalse.s loc_CB5FB
0xcb5d5  ldloc.s  8
0xcb5d7  ldstr    aBehaviorservic// "BehaviorServiceMoveControl"
0xcb5dc  ldc.i4.1
0xcb5dd  newarr   [mscorlib]System.Object
0xcb5e2  dup
0xcb5e3  ldc.i4.0
0xcb5e4  ldarg.1
0xcb5e5  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.Component::get_Site()
0xcb5ea  callvirt instance string [System]System.ComponentModel.ISite::get_Name()
0xcb5ef  stelem.ref
0xcb5f0  call     string System.Design.SR::GetString(string name, object[] args)
0xcb5f5  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0xcb5fa  stloc.0
0xcb5fb  ldnull
0xcb5fc  stloc.s  5
0xcb5fe  ldarg.0
0xcb5ff  ldloc.1
0xcb600  call     instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::PropChanging(class [System]System.ComponentModel.PropertyDescriptor prop)
0xcb605  ldloc.s  4
0xcb607  brfalse.s loc_CB641
0xcb609  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xcb60e  stloc.s  9
0xcb610  ldloc.s  9
0xcb612  ldarg.1
0xcb613  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xcb618  pop
0xcb619  ldloc.s  9
0xcb61b  ldarg.0
0xcb61c  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0xcb621  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0xcb626  call     class [mscorlib]System.Collections.ICollection System.Windows.Forms.Design.DesignerUtils::CopyDragObjects(class [mscorlib]System.Collections.ICollection objects, class [mscorlib]System.IServiceProvider svcProvider)
0xcb62b  isinst   [mscorlib]System.Collections.ArrayList
0xcb630  stloc.s  9
0xcb632  ldloc.s  9
0xcb634  ldc.i4.0
0xcb635  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xcb63a  isinst   [System.Windows.Forms]System.Windows.Forms.Control
0xcb63f  starg.s  1
0xcb641  ldarg.3
0xcb642  brfalse.s loc_CB686
0xcb644  ldarg.0
0xcb645  ldarg.1
0xcb646  call     instance valuetype [System.Drawing]System.Drawing.Point System.Windows.Forms.Design.TableLayoutPanelDesigner::GetControlPosition(class [System.Windows.Forms]System.Windows.Forms.Control control)
0xcb64b  stloc.s  0xA
0xcb64d  ldloc.s  0xA
0xcb64f  ldsfld   valuetype [System.Drawing]System.Drawing.Point System.Windows.Forms.Design.ControlDesigner::InvalidPoint
0xcb654  call     bool [System.Drawing]System.Drawing.Point::op_Inequality(valuetype [System.Drawing]System.Drawing.Point, valuetype [System.Drawing]System.Drawing.Point)
0xcb659  brfalse.s loc_CB686
0xcb65b  ldarg.0
0xcb65c  ldarg.1
0xcb65d  call     instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::RemoveControlInternal(class [System.Windows.Forms]System.Windows.Forms.Control c)
0xcb662  ldloc.s  0xA
0xcb664  ldarg.2
0xcb665  call     bool [System.Drawing]System.Drawing.Point::op_Inequality(valuetype [System.Drawing]System.Drawing.Point, valuetype [System.Drawing]System.Drawing.Point)
0xcb66a  brfalse.s loc_CB686
0xcb66c  ldloc.s  5
0xcb66e  brfalse.s loc_CB686
0xcb670  ldarg.0
0xcb671  ldloc.s  5
0xcb673  ldloca.s 0xA
0xcb675  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0xcb67a  ldloca.s 0xA
0xcb67c  call     instance int32 [System.Drawing]System.Drawing.Point::get_Y()
0xcb681  call     instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::AddControlInternal(class [System.Windows.Forms]System.Windows.Forms.Control c, int32 col, int32 row)
0xcb686  ldarg.3
0xcb687  brfalse.s loc_CB6A0
0xcb689  ldarg.0
0xcb68a  ldarg.1
0xcb68b  ldarga.s 2
0xcb68d  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0xcb692  ldarga.s 2
0xcb694  call     instance int32 [System.Drawing]System.Drawing.Point::get_Y()
0xcb699  call     instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::AddControlInternal(class [System.Windows.Forms]System.Windows.Forms.Control c, int32 col, int32 row)
0xcb69e  br.s     loc_CB6BF
0xcb6a0  ldarg.0
0xcb6a1  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcb6a6  ldarg.1
0xcb6a7  ldarga.s 2
0xcb6a9  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0xcb6ae  ldarga.s 2
0xcb6b0  call     instance int32 [System.Drawing]System.Drawing.Point::get_Y()
0xcb6b5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanelCellPosition::.ctor(int32, int32)
0xcb6ba  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetCellPosition(class [System.Windows.Forms]System.Windows.Forms.Control, valuetype [System.Windows.Forms]System.Windows.Forms.TableLayoutPanelCellPosition)
0xcb6bf  ldarg.0
0xcb6c0  ldloc.1
0xcb6c1  call     instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::PropChanged(class [System]System.ComponentModel.PropertyDescriptor prop)
0xcb6c6  ldarg.s  5
0xcb6c8  brfalse.s loc_CB6D2
0xcb6ca  ldarg.0
0xcb6cb  ldarg.s  5
0xcb6cd  call     instance void System.Windows.Forms.Design.ParentControlDesigner::OnDragComplete(class [System.Windows.Forms]System.Windows.Forms.DragEventArgs de)
0xcb6d2  ldloc.0
0xcb6d3  brfalse.s loc_CB6DD
0xcb6d5  ldloc.0
0xcb6d6  callvirt instance void [System]System.ComponentModel.Design.DesignerTransaction::Commit()
0xcb6db  ldnull
0xcb6dc  stloc.0
0xcb6dd  ldloc.s  4
0xcb6df  brfalse.s loc_CB70F
0xcb6e1  ldarg.0
0xcb6e2  ldtoken  [System]System.ComponentModel.Design.ISelectionService
0xcb6e7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xcb6ec  callvirt instance object System.ComponentModel.Design.ComponentDesigner::GetService(class [mscorlib]System.Type serviceType)
0xcb6f1  isinst   [System]System.ComponentModel.Design.ISelectionService
0xcb6f6  stloc.s  0xB
0xcb6f8  ldloc.s  0xB
0xcb6fa  brfalse.s loc_CB70F
0xcb6fc  ldloc.s  0xB
0xcb6fe  ldc.i4.1
0xcb6ff  newarr   [mscorlib]System.Object
0xcb704  dup
0xcb705  ldc.i4.0
0xcb706  ldarg.1
0xcb707  stelem.ref
0xcb708  ldc.i4.s 0x12
0xcb70a  callvirt instance void [System]System.ComponentModel.Design.ISelectionService::SetSelectedComponents(class [mscorlib]System.Collections.ICollection, valuetype [System]System.ComponentModel.Design.SelectionTypes)
0xcb70f  leave.s  loc_CB752
0xcb711  stloc.s  0xC
  ... truncated ...
```
