# System.Windows.Forms.Design.ControlCommandSet::OnMenuZOrderSelection

- ea: `0xa1910`
- end: `0xa1c1d`
- name: `System.Windows.Forms.Design.ControlCommandSet::OnMenuZOrderSelection`
- size: `781`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x8eec0`
- `0x98ab0`
- `0x98f50`
- `0xa1910`
- `0x116b90`

## string_xrefs

- `0xa19a2`: `CommandSetBringToFront`
- `0xa19c2`: `CommandSetSendToBack`

## pseudocode

```c

```

## disassembly

```asm
0xa1910  ldarg.1
0xa1911  castclass [System]System.ComponentModel.Design.MenuCommand
0xa1916  stloc.0
0xa1917  ldloc.0
0xa1918  callvirt instance class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.MenuCommand::get_CommandID()
0xa191d  stloc.1
0xa191e  ldarg.0
0xa191f  call     instance class [System]System.ComponentModel.Design.ISelectionService System.Windows.Forms.Design.CommandSet::get_SelectionService()
0xa1924  brtrue.s loc_A1927
0xa1926  ret
0xa1927  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xa192c  stloc.2
0xa192d  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xa1932  stloc.3
0xa1933  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursor::get_Current()
0xa1938  stloc.s  4
0xa193a  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_WaitCursor()
0xa193f  call     void [System.Windows.Forms]System.Windows.Forms.Cursor::set_Current(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0xa1944  ldarg.0
0xa1945  ldtoken  [System]System.ComponentModel.Design.IComponentChangeService
0xa194a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa194f  callvirt instance object System.Windows.Forms.Design.CommandSet::GetService(class [mscorlib]System.Type serviceType)
0xa1954  castclass [System]System.ComponentModel.Design.IComponentChangeService
0xa1959  stloc.s  5
0xa195b  ldarg.0
0xa195c  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0xa1961  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa1966  callvirt instance object System.Windows.Forms.Design.CommandSet::GetService(class [mscorlib]System.Type serviceType)
0xa196b  castclass [System]System.ComponentModel.Design.IDesignerHost
0xa1970  stloc.s  6
0xa1972  ldnull
0xa1973  stloc.s  7
0xa1975  ldarg.0
0xa1976  call     instance class [System]System.ComponentModel.Design.ISelectionService System.Windows.Forms.Design.CommandSet::get_SelectionService()
0xa197b  callvirt instance class [mscorlib]System.Collections.ICollection [System]System.ComponentModel.Design.ISelectionService::GetSelectedComponents()
0xa1980  stloc.s  9
0xa1982  ldloc.s  9
0xa1984  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0xa1989  newarr   [mscorlib]System.Object
0xa198e  stloc.s  0xA
0xa1990  ldloc.s  9
0xa1992  ldloc.s  0xA
0xa1994  ldc.i4.0
0xa1995  callvirt instance void [mscorlib]System.Collections.ICollection::CopyTo(class [mscorlib]System.Array, int32)
0xa199a  ldloc.1
0xa199b  ldsfld   class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.StandardCommands::BringToFront
0xa19a0  bne.un.s loc_A19C2
0xa19a2  ldstr    aCommandsetbrin// "CommandSetBringToFront"
0xa19a7  ldc.i4.1
0xa19a8  newarr   [mscorlib]System.Object
0xa19ad  dup
0xa19ae  ldc.i4.0
0xa19af  ldloc.s  0xA
0xa19b1  ldlen
0xa19b2  conv.i4
0xa19b3  box      [mscorlib]System.Int32
0xa19b8  stelem.ref
0xa19b9  call     string System.Design.SR::GetString(string name, object[] args)
0xa19be  stloc.s  8
0xa19c0  br.s     loc_A19E0
0xa19c2  ldstr    aCommandsetsend// "CommandSetSendToBack"
0xa19c7  ldc.i4.1
0xa19c8  newarr   [mscorlib]System.Object
0xa19cd  dup
0xa19ce  ldc.i4.0
0xa19cf  ldloc.s  0xA
0xa19d1  ldlen
0xa19d2  conv.i4
0xa19d3  box      [mscorlib]System.Int32
0xa19d8  stelem.ref
0xa19d9  call     string System.Design.SR::GetString(string name, object[] args)
0xa19de  stloc.s  8
0xa19e0  ldloc.s  0xA
0xa19e2  newobj   instance void ControlComparer::.ctor()
0xa19e7  call     void [mscorlib]System.Array::Sort(class [mscorlib]System.Array, class [mscorlib]System.Collections.IComparer)
0xa19ec  ldloc.s  6
0xa19ee  ldloc.s  8
0xa19f0  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0xa19f5  stloc.s  7
0xa19f7  ldloc.s  0xA
0xa19f9  ldlen
0xa19fa  brfalse  loc_A1B55
0xa19ff  ldloc.s  0xA
0xa1a01  ldlen
0xa1a02  conv.i4
0xa1a03  stloc.s  0xB
0xa1a05  ldloc.s  0xB
0xa1a07  ldc.i4.1
0xa1a08  sub
0xa1a09  stloc.s  0xC
0xa1a0b  br       loc_A1AF5
0xa1a10  ldloc.s  0xA
0xa1a12  ldloc.s  0xC
0xa1a14  ldelem.ref
0xa1a15  isinst   [System.Windows.Forms]System.Windows.Forms.Control
0xa1a1a  stloc.s  0xD
0xa1a1c  ldloc.s  0xA
0xa1a1e  ldloc.s  0xC
0xa1a20  ldelem.ref
0xa1a21  isinst   [System]System.ComponentModel.IComponent
0xa1a26  stloc.s  0xE
0xa1a28  ldloc.s  0xE
0xa1a2a  brfalse.s loc_A1A65
0xa1a2c  ldloc.s  0xE
0xa1a2e  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0xa1a33  isinst   [System]System.ComponentModel.INestedSite
0xa1a38  stloc.s  0xF
0xa1a3a  ldloc.s  0xF
0xa1a3c  brfalse.s loc_A1A65
0xa1a3e  ldloc.s  0xF
0xa1a40  callvirt instance class [System]System.ComponentModel.IContainer [System]System.ComponentModel.ISite::get_Container()
0xa1a45  isinst   [System]System.ComponentModel.INestedContainer
0xa1a4a  stloc.s  0x10
0xa1a4c  ldloc.s  0x10
0xa1a4e  brfalse.s loc_A1A65
0xa1a50  ldloc.s  0x10
0xa1a52  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.INestedContainer::get_Owner()
0xa1a57  isinst   [System.Windows.Forms]System.Windows.Forms.Control
0xa1a5c  stloc.s  0xD
0xa1a5e  ldloc.s  0xA
0xa1a60  ldloc.s  0xC
0xa1a62  ldloc.s  0xD
0xa1a64  stelem.ref
0xa1a65  ldloc.s  0xD
0xa1a67  brfalse  loc_A1AEF
0xa1a6c  ldloc.s  0xD
0xa1a6e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0xa1a73  stloc.s  0x11
0xa1a75  ldnull
0xa1a76  stloc.s  0x12
0xa1a78  ldloc.s  0x11
0xa1a7a  brfalse.s loc_A1AEF
0xa1a7c  ldloc.s  5
0xa1a7e  brfalse.s loc_A1AD5
0xa1a80  ldloc.3
0xa1a81  ldloc.s  0x11
0xa1a83  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0xa1a88  brtrue.s loc_A1AB5
0xa1a8a  ldloc.s  0x11
0xa1a8c  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xa1a91  ldstr    aControls// "Controls"
0xa1a96  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xa1a9b  stloc.s  0x12
0xa1a9d  ldloc.s  0x12
0xa1a9f  brfalse.s loc_A1AB5
0xa1aa1  ldloc.3
0xa1aa2  ldloc.s  0x11
0xa1aa4  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xa1aa9  pop
0xa1aaa  ldloc.s  5
0xa1aac  ldloc.s  0x11
0xa1aae  ldloc.s  0x12
0xa1ab0  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanging(object, class [System]System.ComponentModel.MemberDescriptor)
0xa1ab5  leave.s  loc_A1AD5
0xa1ab7  stloc.s  0x13
0xa1ab9  ldloc.s  0x13
0xa1abb  ldsfld   class [System]System.ComponentModel.Design.CheckoutException [System]System.ComponentModel.Design.CheckoutException::Canceled
0xa1ac0  bne.un.s loc_A1AD2
0xa1ac2  ldloc.s  7
0xa1ac4  brfalse.s loc_A1ACD
0xa1ac6  ldloc.s  7
0xa1ac8  callvirt instance void [System]System.ComponentModel.Design.DesignerTransaction::Cancel()
0xa1acd  leave    loc_A1C1C
0xa1ad2  ldloc.s  0x13
0xa1ad4  throw
0xa1ad5  ldloc.2
0xa1ad6  ldloc.s  0x11
0xa1ad8  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0xa1add  brtrue.s loc_A1AEF
0xa1adf  ldloc.2
0xa1ae0  ldloc.s  0x11
0xa1ae2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xa1ae7  pop
0xa1ae8  ldloc.s  0x11
0xa1aea  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xa1aef  ldloc.s  0xC
0xa1af1  ldc.i4.1
0xa1af2  sub
0xa1af3  stloc.s  0xC
0xa1af5  ldloc.s  0xC
0xa1af7  ldc.i4.0
0xa1af8  bge      loc_A1A10
0xa1afd  ldloc.s  0xB
0xa1aff  ldc.i4.1
0xa1b00  sub
0xa1b01  stloc.s  0x14
0xa1b03  br.s     loc_A1B50
0xa1b05  ldloc.1
0xa1b06  ldsfld   class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.StandardCommands::BringToFront
0xa1b0b  bne.un.s loc_A1B2B
0xa1b0d  ldloc.s  0xA
0xa1b0f  ldloc.s  0xB
0xa1b11  ldloc.s  0x14
0xa1b13  sub
0xa1b14  ldc.i4.1
0xa1b15  sub
0xa1b16  ldelem.ref
0xa1b17  isinst   [System.Windows.Forms]System.Windows.Forms.Control
0xa1b1c  stloc.s  0x15
0xa1b1e  ldloc.s  0x15
0xa1b20  brfalse.s loc_A1B4A
0xa1b22  ldloc.s  0x15
0xa1b24  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::BringToFront()
0xa1b29  br.s     loc_A1B4A
0xa1b2b  ldloc.1
0xa1b2c  ldsfld   class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.StandardCommands::SendToBack
0xa1b31  bne.un.s loc_A1B4A
0xa1b33  ldloc.s  0xA
0xa1b35  ldloc.s  0x14
0xa1b37  ldelem.ref
0xa1b38  isinst   [System.Windows.Forms]System.Windows.Forms.Control
0xa1b3d  stloc.s  0x16
0xa1b3f  ldloc.s  0x16
0xa1b41  brfalse.s loc_A1B4A
0xa1b43  ldloc.s  0x16
0xa1b45  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SendToBack()
0xa1b4a  ldloc.s  0x14
0xa1b4c  ldc.i4.1
0xa1b4d  sub
0xa1b4e  stloc.s  0x14
0xa1b50  ldloc.s  0x14
0xa1b52  ldc.i4.0
0xa1b53  bge.s    loc_A1B05
0xa1b55  leave    loc_A1C1C
0xa1b5a  ldloc.s  7
0xa1b5c  brfalse  loc_A1C13
0xa1b61  ldloc.s  7
0xa1b63  callvirt instance bool [System]System.ComponentModel.Design.DesignerTransaction::get_Canceled()
0xa1b68  brtrue   loc_A1C13
0xa1b6d  ldloc.3
0xa1b6e  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0xa1b73  stloc.s  0x17
0xa1b75  br.s     loc_A1BAD
0xa1b77  ldloc.s  0x17
0xa1b79  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa1b7e  castclass [System.Windows.Forms]System.Windows.Forms.Control
0xa1b83  stloc.s  0x18
0xa1b85  ldloc.s  0x18
0xa1b87  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xa1b8c  ldstr    aControls// "Controls"
0xa1b91  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xa1b96  stloc.s  0x19
0xa1b98  ldloc.s  5
0xa1b9a  brfalse.s loc_A1BAD
0xa1b9c  ldloc.s  0x19
0xa1b9e  brfalse.s loc_A1BAD
0xa1ba0  ldloc.s  5
0xa1ba2  ldloc.s  0x18
0xa1ba4  ldloc.s  0x19
0xa1ba6  ldnull
0xa1ba7  ldnull
0xa1ba8  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanged(object, class [System]System.ComponentModel.MemberDescriptor, object, object)
0xa1bad  ldloc.s  0x17
0xa1baf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa1bb4  brtrue.s loc_A1B77
0xa1bb6  leave.s  loc_A1BCD
0xa1bb8  ldloc.s  0x17
0xa1bba  isinst   [mscorlib]System.IDisposable
0xa1bbf  stloc.s  0x1A
0xa1bc1  ldloc.s  0x1A
0xa1bc3  brfalse.s loc_A1BCC
0xa1bc5  ldloc.s  0x1A
0xa1bc7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa1bcc  endfinally
0xa1bcd  ldloc.2
0xa1bce  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0xa1bd3  stloc.s  0x1B
0xa1bd5  br.s     loc_A1BEC
0xa1bd7  ldloc.s  0x1B
0xa1bd9  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa1bde  castclass [System.Windows.Forms]System.Windows.Forms.Control
0xa1be3  stloc.s  0x1C
0xa1be5  ldloc.s  0x1C
0xa1be7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout()
0xa1bec  ldloc.s  0x1B
0xa1bee  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa1bf3  brtrue.s loc_A1BD7
0xa1bf5  leave.s  loc_A1C0C
0xa1bf7  ldloc.s  0x1B
0xa1bf9  isinst   [mscorlib]System.IDisposable
0xa1bfe  stloc.s  0x1A
0xa1c00  ldloc.s  0x1A
0xa1c02  brfalse.s loc_A1C0B
0xa1c04  ldloc.s  0x1A
0xa1c06  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa1c0b  endfinally
0xa1c0c  ldloc.s  7
0xa1c0e  callvirt instance void [System]System.ComponentModel.Design.DesignerTransaction::Commit()
0xa1c13  endfinally
0xa1c14  ldloc.s  4
0xa1c16  call     void [System.Windows.Forms]System.Windows.Forms.Cursor::set_Current(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0xa1c1b  endfinally
0xa1c1c  ret
```
