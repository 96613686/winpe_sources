# System.Windows.Forms.Design.CommandSet::OnMenuPaste

- ea: `0x9a960`
- end: `0x9b0b9`
- name: `System.Windows.Forms.Design.CommandSet::OnMenuPaste`
- size: `1881`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x584d0`
- `0x584f0`
- `0x8ef40`
- `0x98a80`
- `0x98ab0`
- `0x98f50`
- `0x9a960`
- `0x9c570`
- `0x9c980`
- `0x9d9a0`
- `0xbadf0`
- `0xbae30`
- `0xc15c0`
- `0xc2ce0`
- `0xc2cf0`
- `0xc2d00`
- `0x115190`

## string_xrefs

- `0x9a9d7`: `CF_DESIGNERCOMPONENTS_V2`
- `0x9a9e4`: `CommandSetPaste`

## pseudocode

```c

```

## disassembly

```asm
0x9a960  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursor::get_Current()
0x9a965  stloc.0
0x9a966  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x9a96b  stloc.1
0x9a96c  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_WaitCursor()
0x9a971  call     void [System.Windows.Forms]System.Windows.Forms.Cursor::set_Current(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x9a976  ldnull
0x9a977  stloc.2
0x9a978  ldarg.0
0x9a979  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0x9a97e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a983  callvirt instance object System.Windows.Forms.Design.CommandSet::GetService(class [mscorlib]System.Type serviceType)
0x9a988  castclass [System]System.ComponentModel.Design.IDesignerHost
0x9a98d  stloc.3
0x9a98e  ldloc.3
0x9a98f  brtrue.s loc_9A996
0x9a991  leave    loc_9B0B8
0x9a996  call     class [System.Windows.Forms]System.Windows.Forms.IDataObject [System.Windows.Forms]System.Windows.Forms.Clipboard::GetDataObject()
0x9a99b  stloc.s  4
0x9a99d  ldnull
0x9a99e  stloc.s  5
0x9a9a0  ldc.i4.0
0x9a9a1  stloc.s  6
0x9a9a3  ldnull
0x9a9a4  stloc.s  7
0x9a9a6  ldc.i4.0
0x9a9a7  stloc.s  8
0x9a9a9  ldarg.0
0x9a9aa  ldtoken  System.Windows.Forms.Design.ComponentTray
0x9a9af  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a9b4  callvirt instance object System.Windows.Forms.Design.CommandSet::GetService(class [mscorlib]System.Type serviceType)
0x9a9b9  isinst   System.Windows.Forms.Design.ComponentTray
0x9a9be  stloc.s  7
0x9a9c0  ldloc.s  7
0x9a9c2  brtrue.s loc_9A9C7
0x9a9c4  ldc.i4.0
0x9a9c5  br.s     loc_9A9D3
0x9a9c7  ldloc.s  7
0x9a9c9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x9a9ce  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Layout.ArrangedElementCollection::get_Count()
0x9a9d3  stloc.s  8
0x9a9d5  ldloc.s  4
0x9a9d7  ldstr    aCfDesignercomp// "CF_DESIGNERCOMPONENTS_V2"
0x9a9dc  callvirt instance object [System.Windows.Forms]System.Windows.Forms.IDataObject::GetData(string)
0x9a9e1  stloc.s  9
0x9a9e3  ldloc.3
0x9a9e4  ldstr    aCommandsetpast// "CommandSetPaste"
0x9a9e9  call     string System.Design.SR::GetString(string name)
0x9a9ee  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0x9a9f3  stloc.s  0xA
0x9a9f5  ldloc.s  9
0x9a9f7  isinst   unsigned int8[]
0x9a9fc  stloc.s  0xB
0x9a9fe  ldloc.s  0xB
0x9aa00  brfalse.s loc_9AA57
0x9aa02  ldloc.s  0xB
0x9aa04  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x9aa09  stloc.s  0xC
0x9aa0b  ldloc.s  0xC
0x9aa0d  brfalse  loc_9AA9B
0x9aa12  ldarg.0
0x9aa13  ldtoken  [System]System.ComponentModel.Design.Serialization.IDesignerSerializationService
0x9aa18  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9aa1d  callvirt instance object System.Windows.Forms.Design.CommandSet::GetService(class [mscorlib]System.Type serviceType)
0x9aa22  castclass [System]System.ComponentModel.Design.Serialization.IDesignerSerializationService
0x9aa27  stloc.s  0xD
0x9aa29  ldloc.s  0xD
0x9aa2b  brfalse.s loc_9AA9B
0x9aa2d  newobj   instance void [mscorlib]System.Runtime.Serialization.Formatters.Binary.BinaryFormatter::.ctor()
0x9aa32  stloc.s  0xE
0x9aa34  ldloc.s  0xC
0x9aa36  ldc.i4.0
0x9aa37  conv.i8
0x9aa38  ldc.i4.0
0x9aa39  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x9aa3e  pop
0x9aa3f  ldloc.s  0xE
0x9aa41  ldloc.s  0xC
0x9aa43  callvirt instance object [mscorlib]System.Runtime.Serialization.Formatters.Binary.BinaryFormatter::Deserialize(class [mscorlib]System.IO.Stream)
0x9aa48  stloc.s  0xF
0x9aa4a  ldloc.s  0xD
0x9aa4c  ldloc.s  0xF
0x9aa4e  callvirt instance class [mscorlib]System.Collections.ICollection [System]System.ComponentModel.Design.Serialization.IDesignerSerializationService::Deserialize(object)
0x9aa53  stloc.s  5
0x9aa55  br.s     loc_9AA9B
0x9aa57  ldarg.0
0x9aa58  ldtoken  [System.Drawing]System.Drawing.Design.IToolboxService
0x9aa5d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9aa62  callvirt instance object System.Windows.Forms.Design.CommandSet::GetService(class [mscorlib]System.Type serviceType)
0x9aa67  castclass [System.Drawing]System.Drawing.Design.IToolboxService
0x9aa6c  stloc.s  0x10
0x9aa6e  ldloc.s  0x10
0x9aa70  brfalse.s loc_9AA9B
0x9aa72  ldloc.s  0x10
0x9aa74  ldloc.s  4
0x9aa76  ldloc.3
0x9aa77  callvirt instance bool [System.Drawing]System.Drawing.Design.IToolboxService::IsSupported(object, class [System]System.ComponentModel.Design.IDesignerHost)
0x9aa7c  brfalse.s loc_9AA9B
0x9aa7e  ldloc.s  0x10
0x9aa80  ldloc.s  4
0x9aa82  ldloc.3
0x9aa83  callvirt instance class [System.Drawing]System.Drawing.Design.ToolboxItem [System.Drawing]System.Drawing.Design.IToolboxService::DeserializeToolboxItem(object, class [System]System.ComponentModel.Design.IDesignerHost)
0x9aa88  stloc.s  0x11
0x9aa8a  ldloc.s  0x11
0x9aa8c  brfalse.s loc_9AA9B
0x9aa8e  ldloc.s  0x11
0x9aa90  ldloc.3
0x9aa91  callvirt instance class [System]System.ComponentModel.IComponent[] [System.Drawing]System.Drawing.Design.ToolboxItem::CreateComponents(class [System]System.ComponentModel.Design.IDesignerHost)
0x9aa96  stloc.s  5
0x9aa98  ldc.i4.1
0x9aa99  stloc.s  6
0x9aa9b  ldloc.s  5
0x9aa9d  brfalse  loc_9B060
0x9aaa2  ldloc.s  5
0x9aaa4  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x9aaa9  ldc.i4.0
0x9aaaa  ble      loc_9B060
0x9aaaf  ldloc.s  5
0x9aab1  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x9aab6  newarr   [mscorlib]System.Object
0x9aabb  stloc.s  0x14
0x9aabd  ldloc.s  5
0x9aabf  ldloc.s  0x14
0x9aac1  ldc.i4.0
0x9aac2  callvirt instance void [mscorlib]System.Collections.ICollection::CopyTo(class [mscorlib]System.Array, int32)
0x9aac7  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x9aacc  stloc.s  0x15
0x9aace  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x9aad3  stloc.s  0x16
0x9aad5  ldnull
0x9aad6  stloc.s  0x17
0x9aad8  ldc.i4.0
0x9aad9  stloc.s  0x18
0x9aadb  ldnull
0x9aadc  stloc.s  0x19
0x9aade  ldnull
0x9aadf  stloc.s  0x1A
0x9aae1  ldc.i4.0
0x9aae2  stloc.s  0x1B
0x9aae4  ldloc.3
0x9aae5  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.IDesignerHost::get_RootComponent()
0x9aaea  stloc.s  0x1C
0x9aaec  ldarg.0
0x9aaed  call     instance class [System]System.ComponentModel.Design.ISelectionService System.Windows.Forms.Design.CommandSet::get_SelectionService()
0x9aaf2  callvirt instance object [System]System.ComponentModel.Design.ISelectionService::get_PrimarySelection()
0x9aaf7  castclass [System]System.ComponentModel.IComponent
0x9aafc  stloc.s  0x19
0x9aafe  ldloc.s  0x19
0x9ab00  brtrue.s loc_9AB06
0x9ab02  ldloc.s  0x1C
0x9ab04  stloc.s  0x19
0x9ab06  ldc.i4.0
0x9ab07  stloc.s  0x1B
0x9ab09  ldloc.3
0x9ab0a  ldloc.s  0x19
0x9ab0c  callvirt instance class [System]System.ComponentModel.Design.IDesigner [System]System.ComponentModel.Design.IDesignerHost::GetDesigner(class [System]System.ComponentModel.IComponent)
0x9ab11  isinst   [System]System.ComponentModel.Design.ITreeDesigner
0x9ab16  stloc.s  0x1D
0x9ab18  br.s     loc_9AB45
0x9ab1a  ldloc.s  0x1D
0x9ab1c  isinst   System.Windows.Forms.Design.IOleDragClient
0x9ab21  brfalse.s loc_9AB2C
0x9ab23  ldloc.s  0x1D
0x9ab25  stloc.s  0x1A
0x9ab27  ldc.i4.1
0x9ab28  stloc.s  0x1B
0x9ab2a  br.s     loc_9AB45
0x9ab2c  ldloc.s  0x1D
0x9ab2e  ldloc.s  0x1D
0x9ab30  callvirt instance class [System]System.ComponentModel.Design.IDesigner [System]System.ComponentModel.Design.ITreeDesigner::get_Parent()
0x9ab35  beq.s    loc_9AB4D
0x9ab37  ldloc.s  0x1D
0x9ab39  callvirt instance class [System]System.ComponentModel.Design.IDesigner [System]System.ComponentModel.Design.ITreeDesigner::get_Parent()
0x9ab3e  isinst   [System]System.ComponentModel.Design.ITreeDesigner
0x9ab43  stloc.s  0x1D
0x9ab45  ldloc.s  0x1B
0x9ab47  brtrue.s loc_9AB4D
0x9ab49  ldloc.s  0x1D
0x9ab4b  brtrue.s loc_9AB1A
0x9ab4d  ldloc.s  5
0x9ab4f  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x9ab54  stloc.s  0x20
0x9ab56  br       loc_9AEBE
0x9ab5b  ldloc.s  0x20
0x9ab5d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9ab62  stloc.s  0x21
0x9ab64  ldnull
0x9ab65  stloc.s  0x13
0x9ab67  ldloc.s  0x21
0x9ab69  isinst   [System]System.ComponentModel.IComponent
0x9ab6e  stloc.s  0x12
0x9ab70  ldloc.s  0x21
0x9ab72  isinst   [System]System.ComponentModel.IComponent
0x9ab77  brfalse.s loc_9AB93
0x9ab79  ldloc.s  0x17
0x9ab7b  brfalse.s loc_9ABB0
0x9ab7d  ldloc.s  0x18
0x9ab7f  ldloc.s  0x17
0x9ab81  ldlen
0x9ab82  conv.i4
0x9ab83  bge.s    loc_9ABB0
0x9ab85  ldloc.s  0x17
0x9ab87  ldloc.s  0x18
0x9ab89  dup
0x9ab8a  ldc.i4.1
0x9ab8b  add
0x9ab8c  stloc.s  0x18
0x9ab8e  ldelem.ref
0x9ab8f  stloc.s  0x13
0x9ab91  br.s     loc_9ABB0
0x9ab93  ldloc.s  0x21
0x9ab95  isinst   string[]
0x9ab9a  stloc.s  0x23
0x9ab9c  ldloc.s  0x17
0x9ab9e  brtrue.s loc_9ABB0
0x9aba0  ldloc.s  0x23
0x9aba2  brfalse.s loc_9ABB0
0x9aba4  ldloc.s  0x23
0x9aba6  stloc.s  0x17
0x9aba8  ldc.i4.0
0x9aba9  stloc.s  0x18
0x9abab  br       loc_9AEBE
0x9abb0  ldarg.0
0x9abb1  ldtoken  [System]System.ComponentModel.Design.IEventBindingService
0x9abb6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9abbb  callvirt instance object System.Windows.Forms.Design.CommandSet::GetService(class [mscorlib]System.Type serviceType)
0x9abc0  isinst   [System]System.ComponentModel.Design.IEventBindingService
0x9abc5  stloc.s  0x22
0x9abc7  ldloc.s  0x22
0x9abc9  brfalse.s loc_9AC3F
0x9abcb  ldloc.s  0x22
0x9abcd  ldloc.s  0x12
0x9abcf  call     class [System]System.ComponentModel.EventDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetEvents(object)
0x9abd4  callvirt instance class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.Design.IEventBindingService::GetEventProperties(class [System]System.ComponentModel.EventDescriptorCollection)
0x9abd9  stloc.s  0x24
0x9abdb  ldloc.s  0x24
0x9abdd  callvirt instance class [mscorlib]System.Collections.IEnumerator [System]System.ComponentModel.PropertyDescriptorCollection::GetEnumerator()
0x9abe2  stloc.s  0x25
0x9abe4  br.s     loc_9AC1F
0x9abe6  ldloc.s  0x25
0x9abe8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9abed  castclass [System]System.ComponentModel.PropertyDescriptor
0x9abf2  stloc.s  0x26
0x9abf4  ldloc.s  0x26
0x9abf6  brfalse.s loc_9AC1F
0x9abf8  ldloc.s  0x26
0x9abfa  callvirt instance bool [System]System.ComponentModel.PropertyDescriptor::get_IsReadOnly()
0x9abff  brtrue.s loc_9AC1F
0x9ac01  ldloc.s  0x26
0x9ac03  ldloc.s  0x12
0x9ac05  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0x9ac0a  isinst   [mscorlib]System.String
0x9ac0f  stloc.s  0x27
0x9ac11  ldloc.s  0x27
0x9ac13  brfalse.s loc_9AC1F
0x9ac15  ldloc.s  0x26
0x9ac17  ldloc.s  0x12
0x9ac19  ldnull
0x9ac1a  callvirt instance void [System]System.ComponentModel.PropertyDescriptor::SetValue(object, object)
0x9ac1f  ldloc.s  0x25
0x9ac21  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9ac26  brtrue.s loc_9ABE6
0x9ac28  leave.s  loc_9AC3F
0x9ac2a  ldloc.s  0x25
0x9ac2c  isinst   [mscorlib]System.IDisposable
0x9ac31  stloc.s  0x28
0x9ac33  ldloc.s  0x28
0x9ac35  brfalse.s loc_9AC3E
0x9ac37  ldloc.s  0x28
0x9ac39  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9ac3e  endfinally
0x9ac3f  ldloc.s  0x1B
0x9ac41  brfalse  loc_9AEBE
0x9ac46  ldc.i4.0
0x9ac47  stloc.s  0x29
0x9ac49  ldloc.2
0x9ac4a  brfalse.s loc_9AC94
0x9ac4c  ldloc.2
0x9ac4d  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x9ac52  stloc.s  0x31
0x9ac54  br.s     loc_9AC74
0x9ac56  ldloc.s  0x31
0x9ac58  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9ac5d  castclass [System]System.ComponentModel.Component
0x9ac62  stloc.s  0x32
0x9ac64  ldloc.s  0x32
0x9ac66  ldloc.s  0x21
0x9ac68  isinst   [System]System.ComponentModel.Component
0x9ac6d  bne.un.s loc_9AC74
0x9ac6f  ldc.i4.1
0x9ac70  stloc.s  0x29
0x9ac72  leave.s  loc_9AC94
0x9ac74  ldloc.s  0x31
0x9ac76  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9ac7b  brtrue.s loc_9AC56
0x9ac7d  leave.s  loc_9AC94
0x9ac7f  ldloc.s  0x31
0x9ac81  isinst   [mscorlib]System.IDisposable
0x9ac86  stloc.s  0x28
0x9ac88  ldloc.s  0x28
  ... truncated ...
```
