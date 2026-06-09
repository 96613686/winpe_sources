# System.Windows.Forms.Design.SelectionUIService::System.Windows.Forms.Design.ISelectionUIService.EndDrag

- ea: `0xc7190`
- end: `0xc7292`
- name: `System.Windows.Forms.Design.SelectionUIService::System.Windows.Forms.Design.ISelectionUIService.EndDrag`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x8eec0`
- `0xbaed0`
- `0xbb0b0`
- `0xc60e0`
- `0xc7190`

## string_xrefs

- `0xc71eb`: `DragDropMoveComponents`
- `0xc721d`: `DragDropMoveComponent`

## pseudocode

```c

```

## disassembly

```asm
0xc7190  ldarg.0
0xc7191  ldnull
0xc7192  stfld    object System.Windows.Forms.Design.SelectionUIService::containerDrag
0xc7197  ldarg.0
0xc7198  ldfld    class System.Windows.Forms.Design.ISelectionUIHandler System.Windows.Forms.Design.SelectionUIService::dragHandler
0xc719d  stloc.0
0xc719e  ldarg.0
0xc719f  ldfld    object[] System.Windows.Forms.Design.SelectionUIService::dragComponents
0xc71a4  stloc.1
0xc71a5  ldarg.0
0xc71a6  ldnull
0xc71a7  stfld    class System.Windows.Forms.Design.ISelectionUIHandler System.Windows.Forms.Design.SelectionUIService::dragHandler
0xc71ac  ldarg.0
0xc71ad  ldnull
0xc71ae  stfld    object[] System.Windows.Forms.Design.SelectionUIService::dragComponents
0xc71b3  ldarg.0
0xc71b4  ldc.i4.0
0xc71b5  stfld    valuetype System.Windows.Forms.Design.SelectionRules System.Windows.Forms.Design.SelectionUIService::dragRules
0xc71ba  ldloc.0
0xc71bb  brtrue.s loc_C71C3
0xc71bd  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0xc71c2  throw
0xc71c3  ldnull
0xc71c4  stloc.2
0xc71c5  ldloc.1
0xc71c6  ldc.i4.0
0xc71c7  ldelem.ref
0xc71c8  isinst   [System]System.ComponentModel.IComponent
0xc71cd  stloc.3
0xc71ce  ldloc.1
0xc71cf  ldlen
0xc71d0  conv.i4
0xc71d1  ldc.i4.1
0xc71d2  bgt.s    loc_C71E5
0xc71d4  ldloc.1
0xc71d5  ldlen
0xc71d6  conv.i4
0xc71d7  ldc.i4.1
0xc71d8  bne.un.s loc_C720E
0xc71da  ldloc.3
0xc71db  brfalse.s loc_C720E
0xc71dd  ldloc.3
0xc71de  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0xc71e3  brtrue.s loc_C720E
0xc71e5  ldarg.0
0xc71e6  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.SelectionUIService::host
0xc71eb  ldstr    aDragdropmoveco// "DragDropMoveComponents"
0xc71f0  ldc.i4.1
0xc71f1  newarr   [mscorlib]System.Object
0xc71f6  dup
0xc71f7  ldc.i4.0
0xc71f8  ldloc.1
0xc71f9  ldlen
0xc71fa  conv.i4
0xc71fb  box      [mscorlib]System.Int32
0xc7200  stelem.ref
0xc7201  call     string System.Design.SR::GetString(string name, object[] args)
0xc7206  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0xc720b  stloc.2
0xc720c  br.s     loc_C7241
0xc720e  ldloc.1
0xc720f  ldlen
0xc7210  conv.i4
0xc7211  ldc.i4.1
0xc7212  bne.un.s loc_C7241
0xc7214  ldloc.3
0xc7215  brfalse.s loc_C7241
0xc7217  ldarg.0
0xc7218  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.SelectionUIService::host
0xc721d  ldstr    aDragdropmoveco_0// "DragDropMoveComponent"
0xc7222  ldc.i4.1
0xc7223  newarr   [mscorlib]System.Object
0xc7228  dup
0xc7229  ldc.i4.0
0xc722a  ldloc.3
0xc722b  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0xc7230  callvirt instance string [System]System.ComponentModel.ISite::get_Name()
0xc7235  stelem.ref
0xc7236  call     string System.Design.SR::GetString(string name, object[] args)
0xc723b  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0xc7240  stloc.2
0xc7241  nop
0xc7242  ldloc.0
0xc7243  ldloc.1
0xc7244  ldarg.1
0xc7245  callvirt instance void System.Windows.Forms.Design.ISelectionUIHandler::EndDrag(object[] components, bool cancel)
0xc724a  leave.s  loc_C7291
0xc724c  stloc.s  4
0xc724e  leave.s  loc_C7291
0xc7250  ldloc.2
0xc7251  brfalse.s loc_C7259
0xc7253  ldloc.2
0xc7254  callvirt instance void [System]System.ComponentModel.Design.DesignerTransaction::Commit()
0xc7259  ldarg.0
0xc725a  ldarg.0
0xc725b  ldfld    bool System.Windows.Forms.Design.SelectionUIService::savedVisible
0xc7260  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0xc7265  ldarg.0
0xc7266  callvirt instance void System.Windows.Forms.Design.ISelectionUIService::SyncSelection()
0xc726b  ldarg.0
0xc726c  ldfld    class [System]System.ComponentModel.Design.DesignerTransaction System.Windows.Forms.Design.SelectionUIService::dragTransaction
0xc7271  brfalse.s loc_C7285
0xc7273  ldarg.0
0xc7274  ldfld    class [System]System.ComponentModel.Design.DesignerTransaction System.Windows.Forms.Design.SelectionUIService::dragTransaction
0xc7279  callvirt instance void [System]System.ComponentModel.Design.DesignerTransaction::Commit()
0xc727e  ldarg.0
0xc727f  ldnull
0xc7280  stfld    class [System]System.ComponentModel.Design.DesignerTransaction System.Windows.Forms.Design.SelectionUIService::dragTransaction
0xc7285  ldarg.0
0xc7286  call     valuetype [System.Drawing]System.Drawing.Point [System.Windows.Forms]System.Windows.Forms.Control::get_MousePosition()
0xc728b  call     instance void System.Windows.Forms.Design.SelectionUIService::EndMouseDrag(valuetype [System.Drawing]System.Drawing.Point position)
0xc7290  endfinally
0xc7291  ret
```
