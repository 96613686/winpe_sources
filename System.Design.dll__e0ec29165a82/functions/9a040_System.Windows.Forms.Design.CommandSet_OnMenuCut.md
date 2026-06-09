# System.Windows.Forms.Design.CommandSet::OnMenuCut

- ea: `0x9a040`
- end: `0x9a385`
- name: `System.Windows.Forms.Design.CommandSet::OnMenuCut`
- size: `837`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x8eec0`
- `0x98ab0`
- `0x98dd0`
- `0x98ea0`
- `0x98f50`
- `0x9a040`
- `0x9c420`
- `0xc2ce0`
- `0xc2cf0`
- `0xc2d00`

## string_xrefs

- `0x9a0c1`: `CF_DESIGNERCOMPONENTS_V2`
- `0x9a11a`: `CommandSetCutMultiple`

## pseudocode

```c

```

## disassembly

```asm
0x9a040  ldarg.0
0x9a041  call     instance class [System]System.ComponentModel.Design.ISelectionService System.Windows.Forms.Design.CommandSet::get_SelectionService()
0x9a046  brtrue.s loc_9A049
0x9a048  ret
0x9a049  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursor::get_Current()
0x9a04e  stloc.0
0x9a04f  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_WaitCursor()
0x9a054  call     void [System.Windows.Forms]System.Windows.Forms.Cursor::set_Current(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x9a059  ldarg.0
0x9a05a  callvirt instance class [mscorlib]System.Collections.ICollection System.Windows.Forms.Design.CommandSet::GetCopySelection()
0x9a05f  stloc.1
0x9a060  ldloc.1
0x9a061  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x9a066  stloc.2
0x9a067  ldarg.0
0x9a068  ldloc.1
0x9a069  call     instance class [mscorlib]System.Collections.ICollection System.Windows.Forms.Design.CommandSet::PrependComponentNames(class [mscorlib]System.Collections.ICollection objects)
0x9a06e  stloc.1
0x9a06f  ldarg.0
0x9a070  ldtoken  [System]System.ComponentModel.Design.Serialization.IDesignerSerializationService
0x9a075  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a07a  callvirt instance object System.Windows.Forms.Design.CommandSet::GetService(class [mscorlib]System.Type serviceType)
0x9a07f  castclass [System]System.ComponentModel.Design.Serialization.IDesignerSerializationService
0x9a084  stloc.3
0x9a085  ldloc.3
0x9a086  brfalse  loc_9A37B
0x9a08b  ldloc.3
0x9a08c  ldloc.1
0x9a08d  callvirt instance object [System]System.ComponentModel.Design.Serialization.IDesignerSerializationService::Serialize(class [mscorlib]System.Collections.ICollection)
0x9a092  stloc.s  4
0x9a094  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x9a099  stloc.s  5
0x9a09b  newobj   instance void [mscorlib]System.Runtime.Serialization.Formatters.Binary.BinaryFormatter::.ctor()
0x9a0a0  stloc.s  6
0x9a0a2  ldloc.s  6
0x9a0a4  ldloc.s  5
0x9a0a6  ldloc.s  4
0x9a0a8  callvirt instance void [mscorlib]System.Runtime.Serialization.Formatters.Binary.BinaryFormatter::Serialize(class [mscorlib]System.IO.Stream, object)
0x9a0ad  ldloc.s  5
0x9a0af  ldc.i4.0
0x9a0b0  conv.i8
0x9a0b1  ldc.i4.0
0x9a0b2  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x9a0b7  pop
0x9a0b8  ldloc.s  5
0x9a0ba  callvirt instance unsigned int8[] [mscorlib]System.IO.MemoryStream::GetBuffer()
0x9a0bf  stloc.s  7
0x9a0c1  ldstr    aCfDesignercomp// "CF_DESIGNERCOMPONENTS_V2"
0x9a0c6  ldloc.s  7
0x9a0c8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.DataObject::.ctor(string, object)
0x9a0cd  stloc.s  8
0x9a0cf  ldloc.s  8
0x9a0d1  call     void [System.Windows.Forms]System.Windows.Forms.Clipboard::SetDataObject(object)
0x9a0d6  ldarg.0
0x9a0d7  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0x9a0dc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a0e1  callvirt instance object System.Windows.Forms.Design.CommandSet::GetService(class [mscorlib]System.Type serviceType)
0x9a0e6  castclass [System]System.ComponentModel.Design.IDesignerHost
0x9a0eb  stloc.s  9
0x9a0ed  ldnull
0x9a0ee  stloc.s  0xA
0x9a0f0  ldloc.s  9
0x9a0f2  brfalse  loc_9A37B
0x9a0f7  ldarg.0
0x9a0f8  ldtoken  [System]System.ComponentModel.Design.IComponentChangeService
0x9a0fd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a102  callvirt instance object System.Windows.Forms.Design.CommandSet::GetService(class [mscorlib]System.Type serviceType)
0x9a107  castclass [System]System.ComponentModel.Design.IComponentChangeService
0x9a10c  stloc.s  0xB
0x9a10e  ldnull
0x9a10f  stloc.s  0xC
0x9a111  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x9a116  stloc.s  0xD
0x9a118  ldloc.s  9
0x9a11a  ldstr    aCommandsetcutm// "CommandSetCutMultiple"
0x9a11f  ldc.i4.1
0x9a120  newarr   [mscorlib]System.Object
0x9a125  dup
0x9a126  ldc.i4.0
0x9a127  ldloc.2
0x9a128  box      [mscorlib]System.Int32
0x9a12d  stelem.ref
0x9a12e  call     string System.Design.SR::GetString(string name, object[] args)
0x9a133  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0x9a138  stloc.s  0xC
0x9a13a  ldarg.0
0x9a13b  call     instance class [System]System.ComponentModel.Design.ISelectionService System.Windows.Forms.Design.CommandSet::get_SelectionService()
0x9a140  ldc.i4.0
0x9a141  newarr   [mscorlib]System.Object
0x9a146  ldc.i4.2
0x9a147  callvirt instance void [System]System.ComponentModel.Design.ISelectionService::SetSelectedComponents(class [mscorlib]System.Collections.ICollection, valuetype [System]System.ComponentModel.Design.SelectionTypes)
0x9a14c  ldloc.1
0x9a14d  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x9a152  newarr   [mscorlib]System.Object
0x9a157  stloc.s  0xE
0x9a159  ldloc.1
0x9a15a  ldloc.s  0xE
0x9a15c  ldc.i4.0
0x9a15d  callvirt instance void [mscorlib]System.Collections.ICollection::CopyTo(class [mscorlib]System.Array, int32)
0x9a162  ldc.i4.0
0x9a163  stloc.s  0xF
0x9a165  br.s     loc_9A1DD
0x9a167  ldloc.s  0xE
0x9a169  ldloc.s  0xF
0x9a16b  ldelem.ref
0x9a16c  stloc.s  0x10
0x9a16e  ldloc.s  0x10
0x9a170  isinst   [System]System.ComponentModel.IComponent
0x9a175  stloc.s  0x11
0x9a177  ldloc.s  0x10
0x9a179  ldloc.s  9
0x9a17b  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.IDesignerHost::get_RootComponent()
0x9a180  beq.s    loc_9A1D7
0x9a182  ldloc.s  0x11
0x9a184  brfalse.s loc_9A1D7
0x9a186  ldloc.s  0x10
0x9a188  isinst   [System.Windows.Forms]System.Windows.Forms.Control
0x9a18d  stloc.s  0x12
0x9a18f  ldloc.s  0x12
0x9a191  brfalse.s loc_9A1D7
0x9a193  ldloc.s  0x12
0x9a195  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x9a19a  stloc.s  0x13
0x9a19c  ldloc.s  0x13
0x9a19e  brfalse.s loc_9A1D7
0x9a1a0  ldloc.s  9
0x9a1a2  ldloc.s  0x13
0x9a1a4  callvirt instance class [System]System.ComponentModel.Design.IDesigner [System]System.ComponentModel.Design.IDesignerHost::GetDesigner(class [System]System.ComponentModel.IComponent)
0x9a1a9  isinst   System.Windows.Forms.Design.ParentControlDesigner
0x9a1ae  stloc.s  0x14
0x9a1b0  ldloc.s  0x14
0x9a1b2  brfalse.s loc_9A1D7
0x9a1b4  ldloc.s  0xD
0x9a1b6  ldloc.s  0x14
0x9a1b8  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x9a1bd  brtrue.s loc_9A1D7
0x9a1bf  ldloc.s  0x14
0x9a1c1  callvirt instance void System.Windows.Forms.Design.ParentControlDesigner::SuspendChangingEvents()
0x9a1c6  ldloc.s  0xD
0x9a1c8  ldloc.s  0x14
0x9a1ca  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x9a1cf  pop
0x9a1d0  ldloc.s  0x14
0x9a1d2  callvirt instance void System.Windows.Forms.Design.ParentControlDesigner::ForceComponentChanging()
0x9a1d7  ldloc.s  0xF
0x9a1d9  ldc.i4.1
0x9a1da  add
0x9a1db  stloc.s  0xF
0x9a1dd  ldloc.s  0xF
0x9a1df  ldloc.s  0xE
0x9a1e1  ldlen
0x9a1e2  conv.i4
0x9a1e3  blt.s    loc_9A167
0x9a1e5  ldc.i4.0
0x9a1e6  stloc.s  0x15
0x9a1e8  br       loc_9A2D8
0x9a1ed  ldloc.s  0xE
0x9a1ef  ldloc.s  0x15
0x9a1f1  ldelem.ref
0x9a1f2  stloc.s  0x16
0x9a1f4  ldloc.s  0x16
0x9a1f6  isinst   [System]System.ComponentModel.IComponent
0x9a1fb  stloc.s  0x17
0x9a1fd  ldloc.s  0x16
0x9a1ff  ldloc.s  9
0x9a201  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.IDesignerHost::get_RootComponent()
0x9a206  beq      loc_9A2D2
0x9a20b  ldloc.s  0x17
0x9a20d  brfalse  loc_9A2D2
0x9a212  ldloc.s  0x16
0x9a214  isinst   [System.Windows.Forms]System.Windows.Forms.Control
0x9a219  stloc.s  0x18
0x9a21b  ldloc.s  0xA
0x9a21d  brtrue.s loc_9A22E
0x9a21f  ldloc.s  0x18
0x9a221  brfalse.s loc_9A22E
0x9a223  ldloc.s  0x18
0x9a225  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x9a22a  stloc.s  0xA
0x9a22c  br.s     loc_9A26F
0x9a22e  ldloc.s  0xA
0x9a230  brfalse.s loc_9A26F
0x9a232  ldloc.s  0x18
0x9a234  brfalse.s loc_9A26F
0x9a236  ldloc.s  0x18
0x9a238  stloc.s  0x19
0x9a23a  ldloc.s  0x19
0x9a23c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x9a241  ldloc.s  0xA
0x9a243  beq.s    loc_9A26F
0x9a245  ldloc.s  0xA
0x9a247  ldloc.s  0x19
0x9a249  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::Contains(class [System.Windows.Forms]System.Windows.Forms.Control)
0x9a24e  brtrue.s loc_9A26F
0x9a250  ldloc.s  0x19
0x9a252  ldloc.s  0xA
0x9a254  beq.s    loc_9A261
0x9a256  ldloc.s  0x19
0x9a258  ldloc.s  0xA
0x9a25a  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::Contains(class [System.Windows.Forms]System.Windows.Forms.Control)
0x9a25f  brfalse.s loc_9A26C
0x9a261  ldloc.s  0x19
0x9a263  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x9a268  stloc.s  0xA
0x9a26a  br.s     loc_9A26F
0x9a26c  ldnull
0x9a26d  stloc.s  0xA
0x9a26f  ldloc.s  0x17
0x9a271  brfalse.s loc_9A2D2
0x9a273  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x9a278  stloc.s  0x1A
0x9a27a  ldarg.0
0x9a27b  ldloc.s  0x17
0x9a27d  ldloc.s  9
0x9a27f  ldloc.s  0x1A
0x9a281  call     instance void System.Windows.Forms.Design.CommandSet::GetAssociatedComponents(class [System]System.ComponentModel.IComponent component, class [System]System.ComponentModel.Design.IDesignerHost host, class [mscorlib]System.Collections.ArrayList list)
0x9a286  ldloc.s  0x1A
0x9a288  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x9a28d  stloc.s  0x1B
0x9a28f  br.s     loc_9A2A9
0x9a291  ldloc.s  0x1B
0x9a293  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9a298  castclass [System]System.ComponentModel.IComponent
0x9a29d  stloc.s  0x1C
0x9a29f  ldloc.s  0xB
0x9a2a1  ldloc.s  0x1C
0x9a2a3  ldnull
0x9a2a4  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanging(object, class [System]System.ComponentModel.MemberDescriptor)
0x9a2a9  ldloc.s  0x1B
0x9a2ab  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9a2b0  brtrue.s loc_9A291
0x9a2b2  leave.s  loc_9A2C9
0x9a2b4  ldloc.s  0x1B
0x9a2b6  isinst   [mscorlib]System.IDisposable
0x9a2bb  stloc.s  0x1D
0x9a2bd  ldloc.s  0x1D
0x9a2bf  brfalse.s loc_9A2C8
0x9a2c1  ldloc.s  0x1D
0x9a2c3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9a2c8  endfinally
0x9a2c9  ldloc.s  9
0x9a2cb  ldloc.s  0x17
0x9a2cd  callvirt instance void [System]System.ComponentModel.Design.IDesignerHost::DestroyComponent(class [System]System.ComponentModel.IComponent)
0x9a2d2  ldloc.s  0x15
0x9a2d4  ldc.i4.1
0x9a2d5  add
0x9a2d6  stloc.s  0x15
0x9a2d8  ldloc.s  0x15
0x9a2da  ldloc.s  0xE
0x9a2dc  ldlen
0x9a2dd  conv.i4
0x9a2de  blt      loc_9A1ED
0x9a2e3  leave.s  loc_9A335
0x9a2e5  ldloc.s  0xC
0x9a2e7  brfalse.s loc_9A2F0
0x9a2e9  ldloc.s  0xC
0x9a2eb  callvirt instance void [System]System.ComponentModel.Design.DesignerTransaction::Commit()
0x9a2f0  ldloc.s  0xD
0x9a2f2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x9a2f7  stloc.s  0x1E
0x9a2f9  br.s     loc_9A314
0x9a2fb  ldloc.s  0x1E
0x9a2fd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9a302  castclass System.Windows.Forms.Design.ParentControlDesigner
0x9a307  stloc.s  0x1F
0x9a309  ldloc.s  0x1F
0x9a30b  brfalse.s loc_9A314
0x9a30d  ldloc.s  0x1F
0x9a30f  callvirt instance void System.Windows.Forms.Design.ParentControlDesigner::ResumeChangingEvents()
0x9a314  ldloc.s  0x1E
0x9a316  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9a31b  brtrue.s loc_9A2FB
0x9a31d  leave.s  loc_9A334
0x9a31f  ldloc.s  0x1E
0x9a321  isinst   [mscorlib]System.IDisposable
0x9a326  stloc.s  0x1D
0x9a328  ldloc.s  0x1D
0x9a32a  brfalse.s loc_9A333
0x9a32c  ldloc.s  0x1D
0x9a32e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9a333  endfinally
0x9a334  endfinally
0x9a335  ldloc.s  0xA
0x9a337  brfalse.s loc_9A352
0x9a339  ldarg.0
0x9a33a  call     instance class [System]System.ComponentModel.Design.ISelectionService System.Windows.Forms.Design.CommandSet::get_SelectionService()
0x9a33f  ldc.i4.1
0x9a340  newarr   [mscorlib]System.Object
0x9a345  dup
0x9a346  ldc.i4.0
0x9a347  ldloc.s  0xA
0x9a349  stelem.ref
0x9a34a  ldc.i4.2
0x9a34b  callvirt instance void [System]System.ComponentModel.Design.ISelectionService::SetSelectedComponents(class [mscorlib]System.Collections.ICollection, valuetype [System]System.ComponentModel.Design.SelectionTypes)
0x9a350  leave.s  loc_9A384
0x9a352  ldarg.0
0x9a353  call     instance class [System]System.ComponentModel.Design.ISelectionService System.Windows.Forms.Design.CommandSet::get_SelectionService()
0x9a358  callvirt instance object [System]System.ComponentModel.Design.ISelectionService::get_PrimarySelection()
0x9a35d  brtrue.s loc_9A37B
0x9a35f  ldarg.0
  ... truncated ...
```
