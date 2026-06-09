# System.Windows.Forms.Design.OleDragDropHandler::CreateTool_0

- ea: `0xc00f0`
- end: `0xc03d1`
- name: `System.Windows.Forms.Design.OleDragDropHandler::CreateTool_0`
- size: `737`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xc00d0`
- `0xc2290`

## callees

- `0xb0`
- `0x8eec0`
- `0x8ef40`
- `0xc00f0`
- `0xc03e0`
- `0xc1420`

## string_xrefs

- `0xc0151`: `DesignerBatchCreateTool`
- `0xc0303`: `FailedToCreateComponent`

## pseudocode

```c

```

## disassembly

```asm
0xc00f0  ldarg.0
0xc00f1  ldtoken  [System.Drawing]System.Drawing.Design.IToolboxService
0xc00f6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc00fb  call     instance object System.Windows.Forms.Design.OleDragDropHandler::GetService(class [mscorlib]System.Type t)
0xc0100  castclass [System.Drawing]System.Drawing.Design.IToolboxService
0xc0105  stloc.0
0xc0106  ldarg.0
0xc0107  ldtoken  [System]System.ComponentModel.Design.ISelectionService
0xc010c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc0111  call     instance object System.Windows.Forms.Design.OleDragDropHandler::GetService(class [mscorlib]System.Type t)
0xc0116  castclass [System]System.ComponentModel.Design.ISelectionService
0xc011b  stloc.1
0xc011c  ldarg.0
0xc011d  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0xc0122  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc0127  call     instance object System.Windows.Forms.Design.OleDragDropHandler::GetService(class [mscorlib]System.Type t)
0xc012c  castclass [System]System.ComponentModel.Design.IDesignerHost
0xc0131  stloc.2
0xc0132  ldc.i4.0
0xc0133  newarr   [System]System.ComponentModel.IComponent
0xc0138  stloc.3
0xc0139  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursor::get_Current()
0xc013e  stloc.s  4
0xc0140  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_WaitCursor()
0xc0145  call     void [System.Windows.Forms]System.Windows.Forms.Cursor::set_Current(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0xc014a  ldnull
0xc014b  stloc.s  5
0xc014d  ldloc.2
0xc014e  brfalse.s loc_C0171
0xc0150  ldloc.2
0xc0151  ldstr    aDesignerbatchc// "DesignerBatchCreateTool"
0xc0156  ldc.i4.1
0xc0157  newarr   [mscorlib]System.Object
0xc015c  dup
0xc015d  ldc.i4.0
0xc015e  ldarg.1
0xc015f  callvirt instance string [mscorlib]System.Object::ToString()
0xc0164  stelem.ref
0xc0165  call     string System.Design.SR::GetString(string name, object[] args)
0xc016a  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0xc016f  stloc.s  5
0xc0171  leave.s  loc_C0189
0xc0173  stloc.s  6
0xc0175  ldloc.s  6
0xc0177  ldsfld   class [System]System.ComponentModel.Design.CheckoutException [System]System.ComponentModel.Design.CheckoutException::Canceled
0xc017c  bne.un.s loc_C0186
0xc017e  ldloc.3
0xc017f  stloc.s  7
0xc0181  leave    loc_C03CE
0xc0186  ldloc.s  6
0xc0188  throw
0xc0189  nop
0xc018a  ldloc.2
0xc018b  brfalse.s loc_C01D6
0xc018d  ldarg.0
0xc018e  ldloc.2
0xc018f  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.IDesignerHost::get_RootComponent()
0xc0194  call     instance bool System.Windows.Forms.Design.OleDragDropHandler::CurrentlyLocalizing(class [System]System.ComponentModel.IComponent rootComponent)
0xc0199  brfalse.s loc_C01D6
0xc019b  ldarg.0
0xc019c  ldtoken  [System.Windows.Forms]System.Windows.Forms.Design.IUIService
0xc01a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc01a6  call     instance object System.Windows.Forms.Design.OleDragDropHandler::GetService(class [mscorlib]System.Type t)
0xc01ab  castclass [System.Windows.Forms]System.Windows.Forms.Design.IUIService
0xc01b0  stloc.s  9
0xc01b2  ldloc.s  9
0xc01b4  brfalse.s loc_C01C7
0xc01b6  ldloc.s  9
0xc01b8  ldstr    aLocalizingcann// "LocalizingCannotAdd"
0xc01bd  call     string System.Design.SR::GetString(string name)
0xc01c2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Design.IUIService::ShowMessage(string)
0xc01c7  ldc.i4.0
0xc01c8  newarr   [System]System.ComponentModel.IComponent
0xc01cd  stloc.3
0xc01ce  ldloc.3
0xc01cf  stloc.s  7
0xc01d1  leave    loc_C03CE
0xc01d6  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0xc01db  stloc.s  8
0xc01dd  ldarg.2
0xc01de  brfalse.s loc_C01ED
0xc01e0  ldloc.s  8
0xc01e2  ldstr    aParent// "Parent"
0xc01e7  ldarg.2
0xc01e8  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0xc01ed  ldarg.2
0xc01ee  brfalse.s loc_C01FE
0xc01f0  ldarg.2
0xc01f1  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::get_IsMirrored()
0xc01f6  brfalse.s loc_C01FE
0xc01f8  ldarg.3
0xc01f9  ldarg.s  5
0xc01fb  add
0xc01fc  starg.s  3
0xc01fe  ldarg.s  7
0xc0200  brfalse.s loc_C021B
0xc0202  ldloc.s  8
0xc0204  ldstr    aLocation// "Location"
0xc0209  ldarg.3
0xc020a  ldarg.s  4
0xc020c  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0xc0211  box      [System.Drawing]System.Drawing.Point
0xc0216  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0xc021b  ldarg.s  8
0xc021d  brfalse.s loc_C0239
0xc021f  ldloc.s  8
0xc0221  ldstr    aSize// "Size"
0xc0226  ldarg.s  5
0xc0228  ldarg.s  6
0xc022a  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0xc022f  box      [System.Drawing]System.Drawing.Size
0xc0234  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0xc0239  ldarg.s  9
0xc023b  brfalse.s loc_C024B
0xc023d  ldloc.s  8
0xc023f  ldstr    aToolboxsnapdra// "ToolboxSnapDragDropEventArgs"
0xc0244  ldarg.s  9
0xc0246  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0xc024b  ldarg.1
0xc024c  ldloc.2
0xc024d  ldloc.s  8
0xc024f  callvirt instance class [System]System.ComponentModel.IComponent[] [System.Drawing]System.Drawing.Design.ToolboxItem::CreateComponents(class [System]System.ComponentModel.Design.IDesignerHost, class [mscorlib]System.Collections.IDictionary)
0xc0254  stloc.3
0xc0255  leave    loc_C032C
0xc025a  stloc.s  0xA
0xc025c  ldloc.s  0xA
0xc025e  ldsfld   class [System]System.ComponentModel.Design.CheckoutException [System]System.ComponentModel.Design.CheckoutException::Canceled
0xc0263  bne.un.s loc_C026E
0xc0265  ldc.i4.0
0xc0266  newarr   [System]System.ComponentModel.IComponent
0xc026b  stloc.3
0xc026c  br.s     loc_C0270
0xc026e  rethrow
0xc0270  leave    loc_C032C
0xc0275  stloc.s  0xB
0xc0277  ldarg.0
0xc0278  ldtoken  [System.Windows.Forms]System.Windows.Forms.Design.IUIService
0xc027d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc0282  call     instance object System.Windows.Forms.Design.OleDragDropHandler::GetService(class [mscorlib]System.Type t)
0xc0287  castclass [System.Windows.Forms]System.Windows.Forms.Design.IUIService
0xc028c  stloc.s  0xC
0xc028e  ldloc.s  0xC
0xc0290  brfalse.s loc_C029B
0xc0292  ldloc.s  0xC
0xc0294  ldloc.s  0xB
0xc0296  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Design.IUIService::ShowError(class [mscorlib]System.Exception)
0xc029b  leave    loc_C032C
0xc02a0  stloc.s  0xD
0xc02a2  ldarg.0
0xc02a3  ldtoken  [System.Windows.Forms]System.Windows.Forms.Design.IUIService
0xc02a8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc02ad  call     instance object System.Windows.Forms.Design.OleDragDropHandler::GetService(class [mscorlib]System.Type t)
0xc02b2  castclass [System.Windows.Forms]System.Windows.Forms.Design.IUIService
0xc02b7  stloc.s  0xE
0xc02b9  ldsfld   string [mscorlib]System.String::Empty
0xc02be  stloc.s  0xF
0xc02c0  ldloc.s  0xD
0xc02c2  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0xc02c7  brfalse.s loc_C02D7
0xc02c9  ldloc.s  0xD
0xc02cb  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0xc02d0  callvirt instance string [mscorlib]System.Object::ToString()
0xc02d5  stloc.s  0xF
0xc02d7  ldloc.s  0xF
0xc02d9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc02de  brfalse.s loc_C02E9
0xc02e0  ldloc.s  0xD
0xc02e2  callvirt instance string [mscorlib]System.Object::ToString()
0xc02e7  stloc.s  0xF
0xc02e9  ldloc.s  0xD
0xc02eb  isinst   [mscorlib]System.InvalidOperationException
0xc02f0  brfalse.s loc_C02FB
0xc02f2  ldloc.s  0xD
0xc02f4  callvirt instance string [mscorlib]System.Exception::get_Message()
0xc02f9  stloc.s  0xF
0xc02fb  ldloc.s  0xE
0xc02fd  brfalse.s loc_C0328
0xc02ff  ldloc.s  0xE
0xc0301  ldloc.s  0xD
0xc0303  ldstr    aFailedtocreate// "FailedToCreateComponent"
0xc0308  ldc.i4.2
0xc0309  newarr   [mscorlib]System.Object
0xc030e  dup
0xc030f  ldc.i4.0
0xc0310  ldarg.1
0xc0311  callvirt instance string [System.Drawing]System.Drawing.Design.ToolboxItem::get_DisplayName()
0xc0316  stelem.ref
0xc0317  dup
0xc0318  ldc.i4.1
0xc0319  ldloc.s  0xF
0xc031b  stelem.ref
0xc031c  call     string System.Design.SR::GetString(string name, object[] args)
0xc0321  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Design.IUIService::ShowError(class [mscorlib]System.Exception, string)
0xc0326  br.s     loc_C032A
0xc0328  rethrow
0xc032a  leave.s  loc_C032C
0xc032c  ldloc.3
0xc032d  brtrue.s loc_C0336
0xc032f  ldc.i4.0
0xc0330  newarr   [System]System.ComponentModel.IComponent
0xc0335  stloc.3
0xc0336  leave.s  loc_C0364
0xc0338  ldloc.0
0xc0339  brfalse.s loc_C0350
0xc033b  ldarg.1
0xc033c  ldloc.0
0xc033d  ldloc.2
0xc033e  callvirt instance class [System.Drawing]System.Drawing.Design.ToolboxItem [System.Drawing]System.Drawing.Design.IToolboxService::GetSelectedToolboxItem(class [System]System.ComponentModel.Design.IDesignerHost)
0xc0343  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xc0348  brfalse.s loc_C0350
0xc034a  ldloc.0
0xc034b  callvirt instance void [System.Drawing]System.Drawing.Design.IToolboxService::SelectedToolboxItemUsed()
0xc0350  endfinally
0xc0351  ldloc.s  5
0xc0353  brfalse.s loc_C035C
0xc0355  ldloc.s  5
0xc0357  callvirt instance void [System]System.ComponentModel.Design.DesignerTransaction::Commit()
0xc035c  ldloc.s  4
0xc035e  call     void [System.Windows.Forms]System.Windows.Forms.Cursor::set_Current(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0xc0363  endfinally
0xc0364  ldloc.1
0xc0365  brfalse.s loc_C03BC
0xc0367  ldloc.3
0xc0368  ldlen
0xc0369  brfalse.s loc_C03BC
0xc036b  ldloc.2
0xc036c  brfalse.s loc_C0374
0xc036e  ldloc.2
0xc036f  callvirt instance void [System]System.ComponentModel.Design.IDesignerHost::Activate()
0xc0374  ldloc.3
0xc0375  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(class [mscorlib]System.Collections.ICollection)
0xc037a  stloc.s  0x10
0xc037c  ldc.i4.0
0xc037d  stloc.s  0x11
0xc037f  br.s     loc_C03A7
0xc0381  ldloc.3
0xc0382  ldloc.s  0x11
0xc0384  ldelem.ref
0xc0385  call     class [System]System.ComponentModel.AttributeCollection [System]System.ComponentModel.TypeDescriptor::GetAttributes(object)
0xc038a  ldsfld   class [System]System.ComponentModel.DesignTimeVisibleAttribute [System]System.ComponentModel.DesignTimeVisibleAttribute::Yes
0xc038f  callvirt instance bool [System]System.ComponentModel.AttributeCollection::Contains(class [mscorlib]System.Attribute)
0xc0394  brtrue.s loc_C03A1
0xc0396  ldloc.s  0x10
0xc0398  ldloc.3
0xc0399  ldloc.s  0x11
0xc039b  ldelem.ref
0xc039c  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0xc03a1  ldloc.s  0x11
0xc03a3  ldc.i4.1
0xc03a4  add
0xc03a5  stloc.s  0x11
0xc03a7  ldloc.s  0x11
0xc03a9  ldloc.3
0xc03aa  ldlen
0xc03ab  conv.i4
0xc03ac  blt.s    loc_C0381
0xc03ae  ldloc.1
0xc03af  ldloc.s  0x10
0xc03b1  callvirt instance object[] [mscorlib]System.Collections.ArrayList::ToArray()
0xc03b6  ldc.i4.2
0xc03b7  callvirt instance void [System]System.ComponentModel.Design.ISelectionService::SetSelectedComponents(class [mscorlib]System.Collections.ICollection, valuetype [System]System.ComponentModel.Design.SelectionTypes)
0xc03bc  ldsfld   class Microsoft.Internal.Performance.CodeMarkers System.Windows.Forms.Design.OleDragDropHandler::codemarkers
0xc03c1  ldc.i4   0x1D4D
0xc03c6  callvirt instance bool Microsoft.Internal.Performance.CodeMarkers::CodeMarker(int32 nTimerID)
0xc03cb  pop
0xc03cc  ldloc.3
0xc03cd  ret
0xc03ce  ldloc.s  7
0xc03d0  ret
```
