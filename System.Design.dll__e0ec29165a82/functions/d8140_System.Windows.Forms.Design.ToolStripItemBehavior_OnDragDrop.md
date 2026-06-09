# System.Windows.Forms.Design.ToolStripItemBehavior::OnDragDrop

- ea: `0xd8140`
- end: `0xd85b5`
- name: `System.Windows.Forms.Design.ToolStripItemBehavior::OnDragDrop`
- size: `1141`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `service_task`

## callees

- `0x8eec0`
- `0x8efb0`
- `0xb2d20`
- `0xd7790`
- `0xd77c0`
- `0xd77f0`
- `0xd8140`
- `0xd8970`
- `0xd8990`
- `0xda8c0`
- `0xdf100`
- `0xdf120`
- `0xe53f0`

## string_xrefs

- `0xd81f3`: `BehaviorServiceMoveControl`
- `0xd81fa`: `BehaviorServiceCopyControl`
- `0xd8217`: `BehaviorServiceMoveControls`
- `0xd821e`: `BehaviorServiceCopyControls`

## pseudocode

```c

```

## disassembly

```asm
0xd8140  ldsfld   class [System.Windows.Forms]System.Windows.Forms.ToolStripItem System.Windows.Forms.Design.ToolStripDesigner::dragItem
0xd8145  stloc.0
0xd8146  ldarg.2
0xd8147  callvirt instance class [System.Windows.Forms]System.Windows.Forms.IDataObject [System.Windows.Forms]System.Windows.Forms.DragEventArgs::get_Data()
0xd814c  isinst   System.Windows.Forms.Design.ToolStripItemDataObject
0xd8151  brfalse  loc_D85B4
0xd8156  ldloc.0
0xd8157  brfalse  loc_D85B4
0xd815c  ldarg.2
0xd815d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.IDataObject [System.Windows.Forms]System.Windows.Forms.DragEventArgs::get_Data()
0xd8162  castclass System.Windows.Forms.Design.ToolStripItemDataObject
0xd8167  stloc.1
0xd8168  ldloc.1
0xd8169  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem System.Windows.Forms.Design.ToolStripItemDataObject::get_PrimarySelection()
0xd816e  stloc.2
0xd816f  ldloc.0
0xd8170  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.Component::get_Site()
0xd8175  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0xd817a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd817f  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xd8184  castclass [System]System.ComponentModel.Design.IDesignerHost
0xd8189  stloc.3
0xd818a  ldloc.0
0xd818b  ldloc.2
0xd818c  beq      loc_D85B4
0xd8191  ldloc.3
0xd8192  brfalse  loc_D85B4
0xd8197  ldloc.1
0xd8198  callvirt instance class [mscorlib]System.Collections.ArrayList System.Windows.Forms.Design.ToolStripItemDataObject::get_DragComponents()
0xd819d  stloc.s  4
0xd819f  ldloc.0
0xd81a0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStrip [System.Windows.Forms]System.Windows.Forms.ToolStripItem::GetCurrentParent()
0xd81a5  stloc.s  5
0xd81a7  ldc.i4.m1
0xd81a8  stloc.s  6
0xd81aa  ldarg.2
0xd81ab  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DragDropEffects [System.Windows.Forms]System.Windows.Forms.DragEventArgs::get_Effect()
0xd81b0  ldc.i4.1
0xd81b1  ceq
0xd81b3  stloc.s  8
0xd81b5  ldloc.s  4
0xd81b7  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xd81bc  ldc.i4.1
0xd81bd  bne.un.s loc_D8213
0xd81bf  ldloc.s  4
0xd81c1  ldc.i4.0
0xd81c2  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xd81c7  call     string [System]System.ComponentModel.TypeDescriptor::GetComponentName(object)
0xd81cc  stloc.s  0xA
0xd81ce  ldloc.s  0xA
0xd81d0  brfalse.s loc_D81DB
0xd81d2  ldloc.s  0xA
0xd81d4  callvirt instance int32 [mscorlib]System.String::get_Length()
0xd81d9  brtrue.s loc_D81EF
0xd81db  ldloc.s  4
0xd81dd  ldc.i4.0
0xd81de  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xd81e3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xd81e8  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xd81ed  stloc.s  0xA
0xd81ef  ldloc.s  8
0xd81f1  brtrue.s loc_D81FA
0xd81f3  ldstr    aBehaviorservic// "BehaviorServiceMoveControl"
0xd81f8  br.s     loc_D81FF
0xd81fa  ldstr    aBehaviorservic_0// "BehaviorServiceCopyControl"
0xd81ff  ldc.i4.1
0xd8200  newarr   [mscorlib]System.Object
0xd8205  dup
0xd8206  ldc.i4.0
0xd8207  ldloc.s  0xA
0xd8209  stelem.ref
0xd820a  call     string System.Design.SR::GetString(string name, object[] args)
0xd820f  stloc.s  7
0xd8211  br.s     loc_D823F
0xd8213  ldloc.s  8
0xd8215  brtrue.s loc_D821E
0xd8217  ldstr    aBehaviorservic_1// "BehaviorServiceMoveControls"
0xd821c  br.s     loc_D8223
0xd821e  ldstr    aBehaviorservic_2// "BehaviorServiceCopyControls"
0xd8223  ldc.i4.1
0xd8224  newarr   [mscorlib]System.Object
0xd8229  dup
0xd822a  ldc.i4.0
0xd822b  ldloc.s  4
0xd822d  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xd8232  box      [mscorlib]System.Int32
0xd8237  stelem.ref
0xd8238  call     string System.Design.SR::GetString(string name, object[] args)
0xd823d  stloc.s  7
0xd823f  ldloc.3
0xd8240  ldloc.s  7
0xd8242  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0xd8247  stloc.s  9
0xd8249  ldloc.0
0xd824a  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.Component::get_Site()
0xd824f  ldtoken  [System]System.ComponentModel.Design.IComponentChangeService
0xd8254  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd8259  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xd825e  castclass [System]System.ComponentModel.Design.IComponentChangeService
0xd8263  stloc.s  0xB
0xd8265  ldloc.s  0xB
0xd8267  brfalse.s loc_D82B5
0xd8269  ldloc.s  5
0xd826b  isinst   [System.Windows.Forms]System.Windows.Forms.ToolStripDropDown
0xd8270  stloc.s  0xD
0xd8272  ldloc.s  0xD
0xd8274  brfalse.s loc_D829B
0xd8276  ldloc.s  0xD
0xd8278  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripDropDown::get_OwnerItem()
0xd827d  stloc.s  0xE
0xd827f  ldloc.s  0xB
0xd8281  ldloc.s  0xE
0xd8283  ldloc.s  0xE
0xd8285  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xd828a  ldstr    aDropdownitems// "DropDownItems"
0xd828f  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xd8294  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanging(object, class [System]System.ComponentModel.MemberDescriptor)
0xd8299  br.s     loc_D82B5
0xd829b  ldloc.s  0xB
0xd829d  ldloc.s  5
0xd829f  ldloc.s  5
0xd82a1  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xd82a6  ldstr    aItems// "Items"
0xd82ab  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xd82b0  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanging(object, class [System]System.ComponentModel.MemberDescriptor)
0xd82b5  ldloc.s  8
0xd82b7  brfalse.s loc_D830F
0xd82b9  ldloc.2
0xd82ba  brfalse.s loc_D82C6
0xd82bc  ldloc.s  4
0xd82be  ldloc.2
0xd82bf  callvirt instance int32 [mscorlib]System.Collections.ArrayList::IndexOf(object)
0xd82c4  stloc.s  6
0xd82c6  ldarg.0
0xd82c7  ldloc.2
0xd82c8  call     instance class System.Windows.Forms.Design.ToolStripKeyboardHandlingService System.Windows.Forms.Design.ToolStripItemBehavior::GetKeyBoardHandlingService(class [System.Windows.Forms]System.Windows.Forms.ToolStripItem item)
0xd82cd  stloc.s  0xF
0xd82cf  ldloc.s  0xF
0xd82d1  brfalse.s loc_D82DB
0xd82d3  ldloc.s  0xF
0xd82d5  ldc.i4.1
0xd82d6  callvirt instance void System.Windows.Forms.Design.ToolStripKeyboardHandlingService::set_CopyInProgress(bool value)
0xd82db  ldloc.s  4
0xd82dd  ldloc.0
0xd82de  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.Component::get_Site()
0xd82e3  call     class [mscorlib]System.Collections.ICollection System.Windows.Forms.Design.DesignerUtils::CopyDragObjects(class [mscorlib]System.Collections.ICollection objects, class [mscorlib]System.IServiceProvider svcProvider)
0xd82e8  isinst   [mscorlib]System.Collections.ArrayList
0xd82ed  stloc.s  4
0xd82ef  ldloc.s  0xF
0xd82f1  brfalse.s loc_D82FB
0xd82f3  ldloc.s  0xF
0xd82f5  ldc.i4.0
0xd82f6  callvirt instance void System.Windows.Forms.Design.ToolStripKeyboardHandlingService::set_CopyInProgress(bool value)
0xd82fb  ldloc.s  6
0xd82fd  ldc.i4.m1
0xd82fe  beq.s    loc_D830F
0xd8300  ldloc.s  4
0xd8302  ldloc.s  6
0xd8304  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xd8309  isinst   [System.Windows.Forms]System.Windows.Forms.ToolStripItem
0xd830e  stloc.2
0xd830f  ldarg.2
0xd8310  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DragDropEffects [System.Windows.Forms]System.Windows.Forms.DragEventArgs::get_Effect()
0xd8315  ldc.i4.2
0xd8316  ceq
0xd8318  ldloc.s  8
0xd831a  or
0xd831b  brfalse  loc_D83E6
0xd8320  ldarg.0
0xd8321  ldloc.0
0xd8322  call     instance class [System]System.ComponentModel.Design.ISelectionService System.Windows.Forms.Design.ToolStripItemBehavior::GetSelectionService(class [System.Windows.Forms]System.Windows.Forms.ToolStripItem item)
0xd8327  stloc.s  0x10
0xd8329  ldloc.s  0x10
0xd832b  brfalse  loc_D83E6
0xd8330  ldloc.s  5
0xd8332  isinst   [System.Windows.Forms]System.Windows.Forms.ToolStripOverflow
0xd8337  brfalse.s loc_D834C
0xd8339  ldloc.s  5
0xd833b  castclass [System.Windows.Forms]System.Windows.Forms.ToolStripOverflow
0xd8340  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripDropDown::get_OwnerItem()
0xd8345  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStrip [System.Windows.Forms]System.Windows.Forms.ToolStripItem::get_Owner()
0xd834a  stloc.s  5
0xd834c  ldloc.s  5
0xd834e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xd8353  ldsfld   class [System.Windows.Forms]System.Windows.Forms.ToolStripItem System.Windows.Forms.Design.ToolStripDesigner::dragItem
0xd8358  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::IndexOf(class [System.Windows.Forms]System.Windows.Forms.ToolStripItem)
0xd835d  stloc.s  0x11
0xd835f  ldloc.s  0x11
0xd8361  ldc.i4.m1
0xd8362  beq.s    loc_D83D3
0xd8364  ldc.i4.0
0xd8365  stloc.s  0x12
0xd8367  ldloc.2
0xd8368  brfalse.s loc_D8379
0xd836a  ldloc.s  5
0xd836c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xd8371  ldloc.2
0xd8372  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::IndexOf(class [System.Windows.Forms]System.Windows.Forms.ToolStripItem)
0xd8377  stloc.s  0x12
0xd8379  ldloc.s  0x12
0xd837b  ldc.i4.m1
0xd837c  beq.s    loc_D838A
0xd837e  ldloc.s  0x11
0xd8380  ldloc.s  0x12
0xd8382  ble.s    loc_D838A
0xd8384  ldloc.s  0x11
0xd8386  ldc.i4.1
0xd8387  sub
0xd8388  stloc.s  0x11
0xd838a  ldloc.s  4
0xd838c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0xd8391  stloc.s  0x13
0xd8393  br.s     loc_D83B3
0xd8395  ldloc.s  0x13
0xd8397  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xd839c  castclass [System.Windows.Forms]System.Windows.Forms.ToolStripItem
0xd83a1  stloc.s  0x14
0xd83a3  ldloc.s  5
0xd83a5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xd83aa  ldloc.s  0x11
0xd83ac  ldloc.s  0x14
0xd83ae  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::Insert(int32, class [System.Windows.Forms]System.Windows.Forms.ToolStripItem)
0xd83b3  ldloc.s  0x13
0xd83b5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd83ba  brtrue.s loc_D8395
0xd83bc  leave.s  loc_D83D3
0xd83be  ldloc.s  0x13
0xd83c0  isinst   [mscorlib]System.IDisposable
0xd83c5  stloc.s  0x15
0xd83c7  ldloc.s  0x15
0xd83c9  brfalse.s loc_D83D2
0xd83cb  ldloc.s  0x15
0xd83cd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd83d2  endfinally
0xd83d3  ldloc.s  0x10
0xd83d5  ldc.i4.1
0xd83d6  newarr   [System]System.ComponentModel.IComponent
0xd83db  dup
0xd83dc  ldc.i4.0
0xd83dd  ldloc.2
0xd83de  stelem.ref
0xd83df  ldc.i4.s 0x12
0xd83e1  callvirt instance void [System]System.ComponentModel.Design.ISelectionService::SetSelectedComponents(class [mscorlib]System.Collections.ICollection, valuetype [System]System.ComponentModel.Design.SelectionTypes)
0xd83e6  ldloc.s  0xB
0xd83e8  brfalse  loc_D84BC
0xd83ed  ldloc.s  5
0xd83ef  isinst   [System.Windows.Forms]System.Windows.Forms.ToolStripDropDown
0xd83f4  stloc.s  0x16
0xd83f6  ldloc.s  0x16
0xd83f8  brfalse.s loc_D8421
0xd83fa  ldloc.s  0x16
0xd83fc  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripDropDown::get_OwnerItem()
0xd8401  stloc.s  0x17
0xd8403  ldloc.s  0xB
0xd8405  ldloc.s  0x17
0xd8407  ldloc.s  0x17
0xd8409  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xd840e  ldstr    aDropdownitems// "DropDownItems"
0xd8413  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xd8418  ldnull
0xd8419  ldnull
0xd841a  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanged(object, class [System]System.ComponentModel.MemberDescriptor, object, object)
0xd841f  br.s     loc_D843D
0xd8421  ldloc.s  0xB
0xd8423  ldloc.s  5
0xd8425  ldloc.s  5
0xd8427  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xd842c  ldstr    aItems// "Items"
0xd8431  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xd8436  ldnull
0xd8437  ldnull
0xd8438  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanged(object, class [System]System.ComponentModel.MemberDescriptor, object, object)
0xd843d  ldloc.s  8
0xd843f  brfalse.s loc_D84BC
0xd8441  ldloc.s  0x16
0xd8443  brfalse.s loc_D8486
0xd8445  ldloc.s  0x16
0xd8447  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripDropDown::get_OwnerItem()
0xd844c  stloc.s  0x18
0xd844e  ldloc.s  0xB
0xd8450  ldloc.s  0x18
0xd8452  ldloc.s  0x18
0xd8454  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xd8459  ldstr    aDropdownitems// "DropDownItems"
0xd845e  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xd8463  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanging(object, class [System]System.ComponentModel.MemberDescriptor)
0xd8468  ldloc.s  0xB
0xd846a  ldloc.s  0x18
0xd846c  ldloc.s  0x18
0xd846e  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xd8473  ldstr    aDropdownitems// "DropDownItems"
0xd8478  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xd847d  ldnull
0xd847e  ldnull
0xd847f  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanged(object, class [System]System.ComponentModel.MemberDescriptor, object, object)
0xd8484  br.s     loc_D84BC
0xd8486  ldloc.s  0xB
0xd8488  ldloc.s  5
0xd848a  ldloc.s  5
0xd848c  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
  ... truncated ...
```
