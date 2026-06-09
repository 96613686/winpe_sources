# System.Windows.Forms.Design.CommandSet::OnMenuCenterSelection

- ea: `0x99bd0`
- end: `0x99f9d`
- name: `System.Windows.Forms.Design.CommandSet::OnMenuCenterSelection`
- size: `973`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x8eec0`
- `0x98ab0`
- `0x98f50`
- `0x99030`
- `0x99bd0`

## string_xrefs

- `0x99c3a`: `WindowsFormsCommandCenterX`
- `0x99c5c`: `WindowsFormsCommandCenterY`

## pseudocode

```c

```

## disassembly

```asm
0x99bd0  ldarg.1
0x99bd1  castclass [System]System.ComponentModel.Design.MenuCommand
0x99bd6  stloc.0
0x99bd7  ldloc.0
0x99bd8  callvirt instance class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.MenuCommand::get_CommandID()
0x99bdd  stloc.1
0x99bde  ldarg.0
0x99bdf  call     instance class [System]System.ComponentModel.Design.ISelectionService System.Windows.Forms.Design.CommandSet::get_SelectionService()
0x99be4  brtrue.s loc_99BE7
0x99be6  ret
0x99be7  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursor::get_Current()
0x99bec  stloc.2
0x99bed  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_WaitCursor()
0x99bf2  call     void [System.Windows.Forms]System.Windows.Forms.Cursor::set_Current(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x99bf7  ldarg.0
0x99bf8  call     instance class [System]System.ComponentModel.Design.ISelectionService System.Windows.Forms.Design.CommandSet::get_SelectionService()
0x99bfd  callvirt instance class [mscorlib]System.Collections.ICollection [System]System.ComponentModel.Design.ISelectionService::GetSelectedComponents()
0x99c02  stloc.3
0x99c03  ldnull
0x99c04  stloc.s  4
0x99c06  ldsfld   valuetype [System.Drawing]System.Drawing.Size [System.Drawing]System.Drawing.Size::Empty
0x99c0b  stloc.s  5
0x99c0d  ldsfld   valuetype [System.Drawing]System.Drawing.Point [System.Drawing]System.Drawing.Point::Empty
0x99c12  stloc.s  6
0x99c14  ldarg.0
0x99c15  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0x99c1a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x99c1f  callvirt instance object System.Windows.Forms.Design.CommandSet::GetService(class [mscorlib]System.Type serviceType)
0x99c24  castclass [System]System.ComponentModel.Design.IDesignerHost
0x99c29  stloc.s  7
0x99c2b  ldnull
0x99c2c  stloc.s  8
0x99c2e  ldloc.s  7
0x99c30  brfalse.s loc_99C87
0x99c32  ldloc.1
0x99c33  ldsfld   class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.StandardCommands::CenterHorizontally
0x99c38  bne.un.s loc_99C5C
0x99c3a  ldstr    aWindowsformsco// "WindowsFormsCommandCenterX"
0x99c3f  ldc.i4.1
0x99c40  newarr   [mscorlib]System.Object
0x99c45  dup
0x99c46  ldc.i4.0
0x99c47  ldloc.3
0x99c48  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x99c4d  box      [mscorlib]System.Int32
0x99c52  stelem.ref
0x99c53  call     string System.Design.SR::GetString(string name, object[] args)
0x99c58  stloc.s  0x16
0x99c5a  br.s     loc_99C7C
0x99c5c  ldstr    aWindowsformsco_0// "WindowsFormsCommandCenterY"
0x99c61  ldc.i4.1
0x99c62  newarr   [mscorlib]System.Object
0x99c67  dup
0x99c68  ldc.i4.0
0x99c69  ldloc.3
0x99c6a  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x99c6f  box      [mscorlib]System.Int32
0x99c74  stelem.ref
0x99c75  call     string System.Design.SR::GetString(string name, object[] args)
0x99c7a  stloc.s  0x16
0x99c7c  ldloc.s  7
0x99c7e  ldloc.s  0x16
0x99c80  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0x99c85  stloc.s  8
0x99c87  ldc.i4   0x7FFFFFFF
0x99c8c  stloc.s  9
0x99c8e  ldc.i4   0x7FFFFFFF
0x99c93  stloc.s  0xA
0x99c95  ldc.i4   0x80000000
0x99c9a  stloc.s  0xB
0x99c9c  ldc.i4   0x80000000
0x99ca1  stloc.s  0xC
0x99ca3  ldloc.3
0x99ca4  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x99ca9  stloc.s  0x17
0x99cab  br       loc_99DE0
0x99cb0  ldloc.s  0x17
0x99cb2  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x99cb7  stloc.s  0x18
0x99cb9  ldloc.s  0x18
0x99cbb  isinst   [System.Windows.Forms]System.Windows.Forms.Control
0x99cc0  brfalse  loc_99DE0
0x99cc5  ldloc.s  0x18
0x99cc7  castclass [System]System.ComponentModel.IComponent
0x99ccc  stloc.s  0x19
0x99cce  ldloc.s  0x19
0x99cd0  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x99cd5  stloc.s  0x1A
0x99cd7  ldloc.s  0x1A
0x99cd9  ldstr    aLocation// "Location"
0x99cde  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x99ce3  stloc.s  0x1B
0x99ce5  ldloc.s  0x1A
0x99ce7  ldstr    aSize// "Size"
0x99cec  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x99cf1  stloc.s  0x1C
0x99cf3  ldloc.s  0x1B
0x99cf5  brfalse  loc_99DE0
0x99cfa  ldloc.s  0x1C
0x99cfc  brfalse  loc_99DE0
0x99d01  ldloc.s  0x1B
0x99d03  callvirt instance bool [System]System.ComponentModel.PropertyDescriptor::get_IsReadOnly()
0x99d08  brtrue   loc_99DE0
0x99d0d  ldloc.s  0x1C
0x99d0f  callvirt instance bool [System]System.ComponentModel.PropertyDescriptor::get_IsReadOnly()
0x99d14  brtrue   loc_99DE0
0x99d19  ldloc.s  0x1A
0x99d1b  ldstr    aLocked// "Locked"
0x99d20  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x99d25  stloc.s  0x1D
0x99d27  ldloc.s  0x1D
0x99d29  brfalse.s loc_99D3E
0x99d2b  ldloc.s  0x1D
0x99d2d  ldloc.s  0x19
0x99d2f  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0x99d34  unbox.any [mscorlib]System.Boolean
0x99d39  brtrue   loc_99DE0
0x99d3e  ldloc.s  0x1C
0x99d40  ldloc.s  0x19
0x99d42  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0x99d47  unbox.any [System.Drawing]System.Drawing.Size
0x99d4c  stloc.s  5
0x99d4e  ldloc.s  0x1B
0x99d50  ldloc.s  0x19
0x99d52  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0x99d57  unbox.any [System.Drawing]System.Drawing.Point
0x99d5c  stloc.s  6
0x99d5e  ldloc.s  4
0x99d60  brtrue.s loc_99D70
0x99d62  ldloc.s  0x19
0x99d64  castclass [System.Windows.Forms]System.Windows.Forms.Control
0x99d69  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x99d6e  stloc.s  4
0x99d70  ldloca.s 6
0x99d72  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0x99d77  ldloc.s  0xA
0x99d79  bge.s    loc_99D84
0x99d7b  ldloca.s 6
0x99d7d  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0x99d82  stloc.s  0xA
0x99d84  ldloca.s 6
0x99d86  call     instance int32 [System.Drawing]System.Drawing.Point::get_Y()
0x99d8b  ldloc.s  9
0x99d8d  bge.s    loc_99D98
0x99d8f  ldloca.s 6
0x99d91  call     instance int32 [System.Drawing]System.Drawing.Point::get_Y()
0x99d96  stloc.s  9
0x99d98  ldloca.s 6
0x99d9a  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0x99d9f  ldloca.s 5
0x99da1  call     instance int32 [System.Drawing]System.Drawing.Size::get_Width()
0x99da6  add
0x99da7  ldloc.s  0xB
0x99da9  ble.s    loc_99DBC
0x99dab  ldloca.s 6
0x99dad  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0x99db2  ldloca.s 5
0x99db4  call     instance int32 [System.Drawing]System.Drawing.Size::get_Width()
0x99db9  add
0x99dba  stloc.s  0xB
0x99dbc  ldloca.s 6
0x99dbe  call     instance int32 [System.Drawing]System.Drawing.Point::get_Y()
0x99dc3  ldloca.s 5
0x99dc5  call     instance int32 [System.Drawing]System.Drawing.Size::get_Height()
0x99dca  add
0x99dcb  ldloc.s  0xC
0x99dcd  ble.s    loc_99DE0
0x99dcf  ldloca.s 6
0x99dd1  call     instance int32 [System.Drawing]System.Drawing.Point::get_Y()
0x99dd6  ldloca.s 5
0x99dd8  call     instance int32 [System.Drawing]System.Drawing.Size::get_Height()
0x99ddd  add
0x99dde  stloc.s  0xC
0x99de0  ldloc.s  0x17
0x99de2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x99de7  brtrue   loc_99CB0
0x99dec  leave.s  loc_99E03
0x99dee  ldloc.s  0x17
0x99df0  isinst   [mscorlib]System.IDisposable
0x99df5  stloc.s  0x1E
0x99df7  ldloc.s  0x1E
0x99df9  brfalse.s loc_99E02
0x99dfb  ldloc.s  0x1E
0x99dfd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x99e02  endfinally
0x99e03  ldloc.s  4
0x99e05  brtrue.s loc_99E0C
0x99e07  leave    loc_99F9C
0x99e0c  ldloc.s  0xA
0x99e0e  ldloc.s  0xB
0x99e10  add
0x99e11  ldc.i4.2
0x99e12  div
0x99e13  stloc.s  0xD
0x99e15  ldloc.s  9
0x99e17  ldloc.s  0xC
0x99e19  add
0x99e1a  ldc.i4.2
0x99e1b  div
0x99e1c  stloc.s  0xE
0x99e1e  ldloc.s  4
0x99e20  callvirt instance valuetype [System.Drawing]System.Drawing.Size [System.Windows.Forms]System.Windows.Forms.Control::get_ClientSize()
0x99e25  stloc.s  0x1F
0x99e27  ldloca.s 0x1F
0x99e29  call     instance int32 [System.Drawing]System.Drawing.Size::get_Width()
0x99e2e  ldc.i4.2
0x99e2f  div
0x99e30  stloc.s  0xF
0x99e32  ldloc.s  4
0x99e34  callvirt instance valuetype [System.Drawing]System.Drawing.Size [System.Windows.Forms]System.Windows.Forms.Control::get_ClientSize()
0x99e39  stloc.s  0x1F
0x99e3b  ldloca.s 0x1F
0x99e3d  call     instance int32 [System.Drawing]System.Drawing.Size::get_Height()
0x99e42  ldc.i4.2
0x99e43  div
0x99e44  stloc.s  0x10
0x99e46  ldc.i4.0
0x99e47  stloc.s  0x11
0x99e49  ldc.i4.0
0x99e4a  stloc.s  0x12
0x99e4c  ldc.i4.0
0x99e4d  stloc.s  0x13
0x99e4f  ldc.i4.0
0x99e50  stloc.s  0x14
0x99e52  ldloc.s  0xF
0x99e54  ldloc.s  0xD
0x99e56  blt.s    loc_99E64
0x99e58  ldloc.s  0xF
0x99e5a  ldloc.s  0xD
0x99e5c  sub
0x99e5d  stloc.s  0x11
0x99e5f  ldc.i4.1
0x99e60  stloc.s  0x13
0x99e62  br.s     loc_99E6B
0x99e64  ldloc.s  0xD
0x99e66  ldloc.s  0xF
0x99e68  sub
0x99e69  stloc.s  0x11
0x99e6b  ldloc.s  0x10
0x99e6d  ldloc.s  0xE
0x99e6f  blt.s    loc_99E7D
0x99e71  ldloc.s  0x10
0x99e73  ldloc.s  0xE
0x99e75  sub
0x99e76  stloc.s  0x12
0x99e78  ldc.i4.1
0x99e79  stloc.s  0x14
0x99e7b  br.s     loc_99E84
0x99e7d  ldloc.s  0xE
0x99e7f  ldloc.s  0x10
0x99e81  sub
0x99e82  stloc.s  0x12
0x99e84  ldc.i4.1
0x99e85  stloc.s  0x15
0x99e87  ldloc.3
0x99e88  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x99e8d  stloc.s  0x20
0x99e8f  br       loc_99F66
0x99e94  ldloc.s  0x20
0x99e96  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x99e9b  stloc.s  0x21
0x99e9d  ldloc.s  0x21
0x99e9f  isinst   [System.Windows.Forms]System.Windows.Forms.Control
0x99ea4  brfalse  loc_99F66
0x99ea9  ldloc.s  0x21
0x99eab  castclass [System]System.ComponentModel.IComponent
0x99eb0  stloc.s  0x22
0x99eb2  ldloc.s  0x22
0x99eb4  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x99eb9  stloc.s  0x23
0x99ebb  ldloc.s  0x23
0x99ebd  ldstr    aLocation// "Location"
0x99ec2  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x99ec7  stloc.s  0x24
0x99ec9  ldloc.s  0x24
0x99ecb  callvirt instance bool [System]System.ComponentModel.PropertyDescriptor::get_IsReadOnly()
0x99ed0  brtrue   loc_99F66
0x99ed5  ldloc.s  0x24
0x99ed7  ldloc.s  0x22
0x99ed9  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0x99ede  unbox.any [System.Drawing]System.Drawing.Point
0x99ee3  stloc.s  6
0x99ee5  ldloc.1
0x99ee6  ldsfld   class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.StandardCommands::CenterHorizontally
0x99eeb  bne.un.s loc_99F15
0x99eed  ldloc.s  0x13
0x99eef  brfalse.s loc_99F03
0x99ef1  ldloca.s 6
0x99ef3  dup
0x99ef4  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0x99ef9  ldloc.s  0x11
0x99efb  add
0x99efc  call     instance void [System.Drawing]System.Drawing.Point::set_X(int32)
0x99f01  br.s     loc_99F43
0x99f03  ldloca.s 6
0x99f05  dup
0x99f06  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0x99f0b  ldloc.s  0x11
0x99f0d  sub
0x99f0e  call     instance void [System.Drawing]System.Drawing.Point::set_X(int32)
  ... truncated ...
```
