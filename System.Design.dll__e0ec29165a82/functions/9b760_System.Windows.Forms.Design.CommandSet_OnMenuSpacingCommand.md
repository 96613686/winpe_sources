# System.Windows.Forms.Design.CommandSet::OnMenuSpacingCommand

- ea: `0x9b760`
- end: `0x9bf3e`
- name: `System.Windows.Forms.Design.CommandSet::OnMenuSpacingCommand`
- size: `2014`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x8eec0`
- `0x8ef40`
- `0x98ab0`
- `0x98d40`
- `0x98f40`
- `0x98f50`
- `0x9b760`
- `0x9c4d0`

## string_xrefs

- `0x9b7d2`: `CommandSetFormatSpacing`
- `0x9b8c1`: `CommandSetUnknownSpacingCommand`

## pseudocode

```c

```

## disassembly

```asm
0x9b760  ldarg.1
0x9b761  castclass [System]System.ComponentModel.Design.MenuCommand
0x9b766  stloc.0
0x9b767  ldloc.0
0x9b768  callvirt instance class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.MenuCommand::get_CommandID()
0x9b76d  stloc.1
0x9b76e  ldnull
0x9b76f  stloc.2
0x9b770  ldarg.0
0x9b771  call     instance class [System]System.ComponentModel.Design.ISelectionService System.Windows.Forms.Design.CommandSet::get_SelectionService()
0x9b776  brtrue.s loc_9B779
0x9b778  ret
0x9b779  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursor::get_Current()
0x9b77e  stloc.3
0x9b77f  ldarg.0
0x9b780  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0x9b785  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9b78a  callvirt instance object System.Windows.Forms.Design.CommandSet::GetService(class [mscorlib]System.Type serviceType)
0x9b78f  castclass [System]System.ComponentModel.Design.IDesignerHost
0x9b794  stloc.s  4
0x9b796  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_WaitCursor()
0x9b79b  call     void [System.Windows.Forms]System.Windows.Forms.Cursor::set_Current(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x9b7a0  ldsfld   valuetype [System.Drawing]System.Drawing.Size [System.Drawing]System.Drawing.Size::Empty
0x9b7a5  stloc.s  5
0x9b7a7  ldarg.0
0x9b7a8  call     instance class [System]System.ComponentModel.Design.ISelectionService System.Windows.Forms.Design.CommandSet::get_SelectionService()
0x9b7ad  callvirt instance class [mscorlib]System.Collections.ICollection [System]System.ComponentModel.Design.ISelectionService::GetSelectedComponents()
0x9b7b2  stloc.s  6
0x9b7b4  ldloc.s  6
0x9b7b6  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x9b7bb  newarr   [mscorlib]System.Object
0x9b7c0  stloc.s  7
0x9b7c2  ldloc.s  6
0x9b7c4  ldloc.s  7
0x9b7c6  ldc.i4.0
0x9b7c7  callvirt instance void [mscorlib]System.Collections.ICollection::CopyTo(class [mscorlib]System.Array, int32)
0x9b7cc  ldloc.s  4
0x9b7ce  brfalse.s loc_9B82D
0x9b7d0  ldloc.s  4
0x9b7d2  ldstr    aCommandsetform// "CommandSetFormatSpacing"
0x9b7d7  ldc.i4.1
0x9b7d8  newarr   [mscorlib]System.Object
0x9b7dd  dup
0x9b7de  ldc.i4.0
0x9b7df  ldloc.s  7
0x9b7e1  ldlen
0x9b7e2  conv.i4
0x9b7e3  box      [mscorlib]System.Int32
0x9b7e8  stelem.ref
0x9b7e9  call     string System.Design.SR::GetString(string name, object[] args)
0x9b7ee  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0x9b7f3  stloc.2
0x9b7f4  ldloc.s  4
0x9b7f6  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.IDesignerHost::get_RootComponent()
0x9b7fb  stloc.s  0x17
0x9b7fd  ldloc.s  0x17
0x9b7ff  brfalse.s loc_9B82D
0x9b801  ldloc.s  0x17
0x9b803  isinst   [System.Windows.Forms]System.Windows.Forms.Control
0x9b808  brfalse.s loc_9B82D
0x9b80a  ldarg.0
0x9b80b  ldloc.s  0x17
0x9b80d  ldstr    aCurrentgridsiz// "CurrentGridSize"
0x9b812  call     instance class [System]System.ComponentModel.PropertyDescriptor System.Windows.Forms.Design.CommandSet::GetProperty(object comp, string propName)
0x9b817  stloc.s  0x18
0x9b819  ldloc.s  0x18
0x9b81b  brfalse.s loc_9B82D
0x9b81d  ldloc.s  0x18
0x9b81f  ldloc.s  0x17
0x9b821  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0x9b826  unbox.any [System.Drawing]System.Drawing.Size
0x9b82b  stloc.s  5
0x9b82d  ldarg.0
0x9b82e  ldloc.s  7
0x9b830  ldc.i4   0x40000000
0x9b835  call     instance object[] System.Windows.Forms.Design.CommandSet::FilterSelection(object[] components, valuetype System.Windows.Forms.Design.SelectionRules selectionRules)
0x9b83a  stloc.s  7
0x9b83c  ldc.i4.0
0x9b83d  stloc.s  8
0x9b83f  ldnull
0x9b840  stloc.s  9
0x9b842  ldnull
0x9b843  stloc.s  0xA
0x9b845  ldnull
0x9b846  stloc.s  0xB
0x9b848  ldnull
0x9b849  stloc.s  0xC
0x9b84b  ldsfld   valuetype [System.Drawing]System.Drawing.Size [System.Drawing]System.Drawing.Size::Empty
0x9b850  stloc.s  0xD
0x9b852  ldsfld   valuetype [System.Drawing]System.Drawing.Size [System.Drawing]System.Drawing.Size::Empty
0x9b857  stloc.s  0xE
0x9b859  ldsfld   valuetype [System.Drawing]System.Drawing.Point [System.Drawing]System.Drawing.Point::Empty
0x9b85e  stloc.s  0xF
0x9b860  ldsfld   valuetype [System.Drawing]System.Drawing.Point [System.Drawing]System.Drawing.Point::Empty
0x9b865  stloc.s  0x10
0x9b867  ldsfld   valuetype [System.Drawing]System.Drawing.Point [System.Drawing]System.Drawing.Point::Empty
0x9b86c  stloc.s  0x11
0x9b86e  ldnull
0x9b86f  stloc.s  0x12
0x9b871  ldnull
0x9b872  stloc.s  0x13
0x9b874  ldc.i4.m1
0x9b875  stloc.s  0x14
0x9b877  ldloc.1
0x9b878  ldsfld   class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.StandardCommands::HorizSpaceConcatenate
0x9b87d  beq.s    loc_9B897
0x9b87f  ldloc.1
0x9b880  ldsfld   class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.StandardCommands::HorizSpaceDecrease
0x9b885  beq.s    loc_9B897
0x9b887  ldloc.1
0x9b888  ldsfld   class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.StandardCommands::HorizSpaceIncrease
0x9b88d  beq.s    loc_9B897
0x9b88f  ldloc.1
0x9b890  ldsfld   class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.StandardCommands::HorizSpaceMakeEqual
0x9b895  bne.un.s loc_9B89C
0x9b897  ldc.i4.0
0x9b898  stloc.s  0x14
0x9b89a  br.s     loc_9B8D1
0x9b89c  ldloc.1
0x9b89d  ldsfld   class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.StandardCommands::VertSpaceConcatenate
0x9b8a2  beq.s    loc_9B8BC
0x9b8a4  ldloc.1
0x9b8a5  ldsfld   class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.StandardCommands::VertSpaceDecrease
0x9b8aa  beq.s    loc_9B8BC
0x9b8ac  ldloc.1
0x9b8ad  ldsfld   class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.StandardCommands::VertSpaceIncrease
0x9b8b2  beq.s    loc_9B8BC
0x9b8b4  ldloc.1
0x9b8b5  ldsfld   class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.StandardCommands::VertSpaceMakeEqual
0x9b8ba  bne.un.s loc_9B8C1
0x9b8bc  ldc.i4.1
0x9b8bd  stloc.s  0x14
0x9b8bf  br.s     loc_9B8D1
0x9b8c1  ldstr    aCommandsetunkn// "CommandSetUnknownSpacingCommand"
0x9b8c6  call     string System.Design.SR::GetString(string name)
0x9b8cb  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x9b8d0  throw
0x9b8d1  ldarg.0
0x9b8d2  ldloc.s  7
0x9b8d4  ldloc.s  0x14
0x9b8d6  call     instance void System.Windows.Forms.Design.CommandSet::SortSelection(object[] selectedObjects, int32 nSortBy)
0x9b8db  ldarg.0
0x9b8dc  call     instance class [System]System.ComponentModel.Design.ISelectionService System.Windows.Forms.Design.CommandSet::get_SelectionService()
0x9b8e1  callvirt instance object [System]System.ComponentModel.Design.ISelectionService::get_PrimarySelection()
0x9b8e6  stloc.s  0x15
0x9b8e8  ldc.i4.0
0x9b8e9  stloc.s  0x16
0x9b8eb  ldloc.s  0x15
0x9b8ed  brfalse.s loc_9B8FA
0x9b8ef  ldloc.s  7
0x9b8f1  ldloc.s  0x15
0x9b8f3  call     T0x2B000010
0x9b8f8  stloc.s  0x16
0x9b8fa  ldloc.1
0x9b8fb  ldsfld   class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.StandardCommands::HorizSpaceMakeEqual
0x9b900  beq.s    loc_9B90D
0x9b902  ldloc.1
0x9b903  ldsfld   class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.StandardCommands::VertSpaceMakeEqual
0x9b908  bne.un   loc_9BB23
0x9b90d  ldc.i4.0
0x9b90e  stloc.s  0x19
0x9b910  ldc.i4.0
0x9b911  stloc.s  0x1A
0x9b913  br.s     loc_9B977
0x9b915  ldsfld   valuetype [System.Drawing]System.Drawing.Size [System.Drawing]System.Drawing.Size::Empty
0x9b91a  stloc.s  0xD
0x9b91c  ldloc.s  7
0x9b91e  ldloc.s  0x1A
0x9b920  ldelem.ref
0x9b921  isinst   [System]System.ComponentModel.IComponent
0x9b926  stloc.s  0x1B
0x9b928  ldloc.s  0x1B
0x9b92a  brfalse.s loc_9B953
0x9b92c  ldloc.s  0x1B
0x9b92e  stloc.s  0x12
0x9b930  ldarg.0
0x9b931  ldloc.s  0x12
0x9b933  ldstr    aSize// "Size"
0x9b938  call     instance class [System]System.ComponentModel.PropertyDescriptor System.Windows.Forms.Design.CommandSet::GetProperty(object comp, string propName)
0x9b93d  stloc.s  9
0x9b93f  ldloc.s  9
0x9b941  brfalse.s loc_9B953
0x9b943  ldloc.s  9
0x9b945  ldloc.s  0x12
0x9b947  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0x9b94c  unbox.any [System.Drawing]System.Drawing.Size
0x9b951  stloc.s  0xD
0x9b953  ldloc.s  0x14
0x9b955  brtrue.s loc_9B965
0x9b957  ldloc.s  0x19
0x9b959  ldloca.s 0xD
0x9b95b  call     instance int32 [System.Drawing]System.Drawing.Size::get_Width()
0x9b960  add
0x9b961  stloc.s  0x19
0x9b963  br.s     loc_9B971
0x9b965  ldloc.s  0x19
0x9b967  ldloca.s 0xD
0x9b969  call     instance int32 [System.Drawing]System.Drawing.Size::get_Height()
0x9b96e  add
0x9b96f  stloc.s  0x19
0x9b971  ldloc.s  0x1A
0x9b973  ldc.i4.1
0x9b974  add
0x9b975  stloc.s  0x1A
0x9b977  ldloc.s  0x1A
0x9b979  ldloc.s  7
0x9b97b  ldlen
0x9b97c  conv.i4
0x9b97d  blt.s    loc_9B915
0x9b97f  ldnull
0x9b980  dup
0x9b981  stloc.s  0x12
0x9b983  stloc.s  0x13
0x9b985  ldsfld   valuetype [System.Drawing]System.Drawing.Size [System.Drawing]System.Drawing.Size::Empty
0x9b98a  stloc.s  0xD
0x9b98c  ldsfld   valuetype [System.Drawing]System.Drawing.Point [System.Drawing]System.Drawing.Point::Empty
0x9b991  stloc.s  0xF
0x9b993  ldc.i4.0
0x9b994  stloc.s  0x1A
0x9b996  br       loc_9BA26
0x9b99b  ldloc.s  7
0x9b99d  ldloc.s  0x1A
0x9b99f  ldelem.ref
0x9b9a0  isinst   [System]System.ComponentModel.IComponent
0x9b9a5  stloc.s  0x12
0x9b9a7  ldloc.s  0x12
0x9b9a9  brfalse.s loc_9BA20
0x9b9ab  ldloc.s  0x13
0x9b9ad  brfalse.s loc_9B9C4
0x9b9af  ldloc.s  0x12
0x9b9b1  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x9b9b6  ldloc.s  0x13
0x9b9b8  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x9b9bd  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9b9c2  brfalse.s loc_9B9E2
0x9b9c4  ldarg.0
0x9b9c5  ldloc.s  0x12
0x9b9c7  ldstr    aSize// "Size"
0x9b9cc  call     instance class [System]System.ComponentModel.PropertyDescriptor System.Windows.Forms.Design.CommandSet::GetProperty(object comp, string propName)
0x9b9d1  stloc.s  9
0x9b9d3  ldarg.0
0x9b9d4  ldloc.s  0x12
0x9b9d6  ldstr    aLocation// "Location"
0x9b9db  call     instance class [System]System.ComponentModel.PropertyDescriptor System.Windows.Forms.Design.CommandSet::GetProperty(object comp, string propName)
0x9b9e0  stloc.s  0xB
0x9b9e2  ldloc.s  0x12
0x9b9e4  stloc.s  0x13
0x9b9e6  ldloc.s  0xB
0x9b9e8  brfalse.s loc_9BA20
0x9b9ea  ldloc.s  0xB
0x9b9ec  ldloc.s  0x12
0x9b9ee  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0x9b9f3  unbox.any [System.Drawing]System.Drawing.Point
0x9b9f8  stloc.s  0xF
0x9b9fa  ldloc.s  9
0x9b9fc  brfalse.s loc_9BA20
0x9b9fe  ldloc.s  9
0x9ba00  ldloc.s  0x12
0x9ba02  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0x9ba07  unbox.any [System.Drawing]System.Drawing.Size
0x9ba0c  stloc.s  0xD
0x9ba0e  ldloca.s 0xD
0x9ba10  call     instance bool [System.Drawing]System.Drawing.Size::get_IsEmpty()
0x9ba15  brtrue.s loc_9BA20
0x9ba17  ldloca.s 0xF
0x9ba19  call     instance bool [System.Drawing]System.Drawing.Point::get_IsEmpty()
0x9ba1e  brfalse.s loc_9BA31
0x9ba20  ldloc.s  0x1A
0x9ba22  ldc.i4.1
0x9ba23  add
0x9ba24  stloc.s  0x1A
0x9ba26  ldloc.s  0x1A
0x9ba28  ldloc.s  7
0x9ba2a  ldlen
0x9ba2b  conv.i4
0x9ba2c  blt      loc_9B99B
0x9ba31  ldloc.s  7
0x9ba33  ldlen
0x9ba34  conv.i4
0x9ba35  ldc.i4.1
0x9ba36  sub
0x9ba37  stloc.s  0x1A
0x9ba39  br       loc_9BABF
0x9ba3e  ldloc.s  7
0x9ba40  ldloc.s  0x1A
0x9ba42  ldelem.ref
0x9ba43  isinst   [System]System.ComponentModel.IComponent
0x9ba48  stloc.s  0x12
0x9ba4a  ldloc.s  0x12
0x9ba4c  brfalse.s loc_9BAB9
0x9ba4e  ldloc.s  0x13
0x9ba50  brfalse.s loc_9BA67
0x9ba52  ldloc.s  0x12
0x9ba54  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x9ba59  ldloc.s  0x13
0x9ba5b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x9ba60  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9ba65  brfalse.s loc_9BA85
0x9ba67  ldarg.0
0x9ba68  ldloc.s  0x12
  ... truncated ...
```
