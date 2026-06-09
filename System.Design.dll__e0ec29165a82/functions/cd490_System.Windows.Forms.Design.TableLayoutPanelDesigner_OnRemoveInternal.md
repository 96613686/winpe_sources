# System.Windows.Forms.Design.TableLayoutPanelDesigner::OnRemoveInternal

- ea: `0xcd490`
- end: `0xcd63b`
- name: `System.Windows.Forms.Design.TableLayoutPanelDesigner::OnRemoveInternal`
- size: `427`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0xcd640`
- `0xcd670`

## callees

- `0x58ca0`
- `0x8eec0`
- `0xb2ed0`
- `0xcadf0`
- `0xcd280`
- `0xcd3c0`
- `0xcd490`
- `0xcdb40`
- `0xcdb60`

## string_xrefs

- `0xcd4df`: `TableLayoutPanelDesignerRemoveColumnUndoUnit`
- `0xcd4e6`: `TableLayoutPanelDesignerRemoveRowUndoUnit`

## pseudocode

```c

```

## disassembly

```asm
0xcd490  ldarg.1
0xcd491  brtrue.s loc_CD4A0
0xcd493  ldarg.0
0xcd494  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcd499  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnCount()
0xcd49e  br.s     loc_CD4AB
0xcd4a0  ldarg.0
0xcd4a1  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcd4a6  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowCount()
0xcd4ab  ldc.i4.2
0xcd4ac  bge.s    loc_CD4AF
0xcd4ae  ret
0xcd4af  ldarg.0
0xcd4b0  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0xcd4b5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xcd4ba  callvirt instance object System.ComponentModel.Design.ComponentDesigner::GetService(class [mscorlib]System.Type serviceType)
0xcd4bf  isinst   [System]System.ComponentModel.Design.IDesignerHost
0xcd4c4  stloc.0
0xcd4c5  ldloc.0
0xcd4c6  brfalse  loc_CD63A
0xcd4cb  ldarg.0
0xcd4cc  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcd4d1  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.Component::get_Site()
0xcd4d6  brfalse  loc_CD63A
0xcd4db  ldloc.0
0xcd4dc  ldarg.1
0xcd4dd  brtrue.s loc_CD4E6
0xcd4df  ldstr    aTablelayoutpan_26// "TableLayoutPanelDesignerRemoveColumnUnd"...
0xcd4e4  br.s     loc_CD4EB
0xcd4e6  ldstr    aTablelayoutpan_27// "TableLayoutPanelDesignerRemoveRowUndoUn"...
0xcd4eb  ldc.i4.1
0xcd4ec  newarr   [mscorlib]System.Object
0xcd4f1  dup
0xcd4f2  ldc.i4.0
0xcd4f3  ldarg.0
0xcd4f4  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcd4f9  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.Component::get_Site()
0xcd4fe  callvirt instance string [System]System.ComponentModel.ISite::get_Name()
0xcd503  stelem.ref
0xcd504  call     string System.Design.SR::GetString(string name, object[] args)
0xcd509  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0xcd50e  stloc.1
0xcd50f  ldarg.0
0xcd510  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcd515  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xcd51a  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xcd51f  stloc.2
0xcd520  ldarg.0
0xcd521  ldarg.1
0xcd522  ldarg.2
0xcd523  ldloc.2
0xcd524  call     instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::FixUpControlsOnDelete(bool isRow, int32 index, class [mscorlib]System.Collections.ArrayList deleteList)
0xcd529  ldarg.0
0xcd52a  ldarg.1
0xcd52b  ldarg.2
0xcd52c  call     instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::DeleteRowCol(bool isRow, int32 index)
0xcd531  ldloc.2
0xcd532  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xcd537  ldc.i4.0
0xcd538  ble      loc_CD5FE
0xcd53d  ldarg.0
0xcd53e  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcd543  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xcd548  ldstr    aControls// "Controls"
0xcd54d  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xcd552  stloc.3
0xcd553  ldarg.0
0xcd554  ldloc.3
0xcd555  call     instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::PropChanging(class [System]System.ComponentModel.PropertyDescriptor prop)
0xcd55a  ldloc.2
0xcd55b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0xcd560  stloc.s  4
0xcd562  br.s     loc_CD5D7
0xcd564  ldloc.s  4
0xcd566  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xcd56b  stloc.s  5
0xcd56d  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xcd572  stloc.s  6
0xcd574  ldloc.s  5
0xcd576  castclass [System]System.ComponentModel.IComponent
0xcd57b  ldloc.0
0xcd57c  ldloc.s  6
0xcd57e  call     void System.Windows.Forms.Design.DesignerUtils::GetAssociatedComponents(class [System]System.ComponentModel.IComponent component, class [System]System.ComponentModel.Design.IDesignerHost host, class [mscorlib]System.Collections.ArrayList list)
0xcd583  ldloc.s  6
0xcd585  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0xcd58a  stloc.s  7
0xcd58c  br.s     loc_CD5AA
0xcd58e  ldloc.s  7
0xcd590  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xcd595  castclass [System]System.ComponentModel.IComponent
0xcd59a  stloc.s  8
0xcd59c  ldarg.0
0xcd59d  ldfld    class [System]System.ComponentModel.Design.IComponentChangeService System.Windows.Forms.Design.TableLayoutPanelDesigner::compSvc
0xcd5a2  ldloc.s  8
0xcd5a4  ldnull
0xcd5a5  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanging(object, class [System]System.ComponentModel.MemberDescriptor)
0xcd5aa  ldloc.s  7
0xcd5ac  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xcd5b1  brtrue.s loc_CD58E
0xcd5b3  leave.s  loc_CD5CA
0xcd5b5  ldloc.s  7
0xcd5b7  isinst   [mscorlib]System.IDisposable
0xcd5bc  stloc.s  9
0xcd5be  ldloc.s  9
0xcd5c0  brfalse.s loc_CD5C9
0xcd5c2  ldloc.s  9
0xcd5c4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcd5c9  endfinally
0xcd5ca  ldloc.0
0xcd5cb  ldloc.s  5
0xcd5cd  isinst   [System]System.ComponentModel.Component
0xcd5d2  callvirt instance void [System]System.ComponentModel.Design.IDesignerHost::DestroyComponent(class [System]System.ComponentModel.IComponent)
0xcd5d7  ldloc.s  4
0xcd5d9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xcd5de  brtrue.s loc_CD564
0xcd5e0  leave.s  loc_CD5F7
0xcd5e2  ldloc.s  4
0xcd5e4  isinst   [mscorlib]System.IDisposable
0xcd5e9  stloc.s  9
0xcd5eb  ldloc.s  9
0xcd5ed  brfalse.s loc_CD5F6
0xcd5ef  ldloc.s  9
0xcd5f1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcd5f6  endfinally
0xcd5f7  ldarg.0
0xcd5f8  ldloc.3
0xcd5f9  call     instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::PropChanged(class [System]System.ComponentModel.PropertyDescriptor prop)
0xcd5fe  ldarg.0
0xcd5ff  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcd604  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout()
0xcd609  ldloc.1
0xcd60a  callvirt instance void [System]System.ComponentModel.Design.DesignerTransaction::Commit()
0xcd60f  leave.s  loc_CD63A
0xcd611  stloc.s  0xA
0xcd613  ldsfld   class [System]System.ComponentModel.Design.CheckoutException [System]System.ComponentModel.Design.CheckoutException::Canceled
0xcd618  ldloc.s  0xA
0xcd61a  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xcd61f  brfalse.s loc_CD62C
0xcd621  ldloc.1
0xcd622  brfalse.s loc_CD62E
0xcd624  ldloc.1
0xcd625  callvirt instance void [System]System.ComponentModel.Design.DesignerTransaction::Cancel()
0xcd62a  br.s     loc_CD62E
0xcd62c  rethrow
0xcd62e  leave.s  loc_CD63A
0xcd630  ldloc.1
0xcd631  brfalse.s loc_CD639
0xcd633  ldloc.1
0xcd634  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcd639  endfinally
0xcd63a  ret
```
