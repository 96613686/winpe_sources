# System.Web.UI.WebControls.CommandField::InitializeCell

- ea: `0x9c490`
- end: `0x9c6a3`
- name: `System.Web.UI.WebControls.CommandField::InitializeCell`
- size: `531`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x611a0`
- `0x66310`
- `0x6e560`
- `0x94690`
- `0x94750`
- `0x9bb10`
- `0x9bb70`
- `0x9bc00`
- `0x9bc60`
- `0x9bcc0`
- `0x9bd20`
- `0x9bd80`
- `0x9bde0`
- `0x9be40`
- `0x9bea0`
- `0x9bf00`
- `0x9bf60`
- `0x9bfc0`
- `0x9c020`
- `0x9c080`
- `0x9c0e0`
- `0x9c140`
- `0x9c1a0`
- `0x9c200`
- `0x9c260`
- `0x9c490`
- `0xa2540`

## string_xrefs

- `0x9c4ee`: `Update`
- `0x9c5fb`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x9c490  ldarg.0
0x9c491  ldarg.1
0x9c492  ldarg.2
0x9c493  ldarg.3
0x9c494  ldarg.s  4
0x9c496  call     instance void System.Web.UI.WebControls.DataControlField::InitializeCell(class System.Web.UI.WebControls.DataControlFieldCell cell, valuetype System.Web.UI.WebControls.DataControlCellType cellType, valuetype System.Web.UI.WebControls.DataControlRowState rowState, int32 rowIndex)
0x9c49b  ldarg.0
0x9c49c  callvirt instance bool System.Web.UI.WebControls.CommandField::get_ShowEditButton()
0x9c4a1  stloc.0
0x9c4a2  ldarg.0
0x9c4a3  callvirt instance bool System.Web.UI.WebControls.CommandField::get_ShowDeleteButton()
0x9c4a8  stloc.1
0x9c4a9  ldarg.0
0x9c4aa  callvirt instance bool System.Web.UI.WebControls.CommandField::get_ShowInsertButton()
0x9c4af  stloc.2
0x9c4b0  ldarg.0
0x9c4b1  callvirt instance bool System.Web.UI.WebControls.CommandField::get_ShowSelectButton()
0x9c4b6  stloc.3
0x9c4b7  ldarg.0
0x9c4b8  callvirt instance bool System.Web.UI.WebControls.CommandField::get_ShowCancelButton()
0x9c4bd  stloc.s  4
0x9c4bf  ldc.i4.1
0x9c4c0  stloc.s  5
0x9c4c2  ldarg.0
0x9c4c3  callvirt instance bool System.Web.UI.WebControls.ButtonFieldBase::get_CausesValidation()
0x9c4c8  stloc.s  6
0x9c4ca  ldarg.0
0x9c4cb  callvirt instance string System.Web.UI.WebControls.ButtonFieldBase::get_ValidationGroup()
0x9c4d0  stloc.s  7
0x9c4d2  ldarg.2
0x9c4d3  ldc.i4.2
0x9c4d4  bne.un   loc_9C6A2
0x9c4d9  ldarg.3
0x9c4da  ldc.i4.s 0xC
0x9c4dc  and
0x9c4dd  brfalse  loc_9C5B3
0x9c4e2  ldarg.3
0x9c4e3  ldc.i4.4
0x9c4e4  and
0x9c4e5  ldc.i4.0
0x9c4e6  cgt.un
0x9c4e8  ldloc.0
0x9c4e9  and
0x9c4ea  brfalse.s loc_9C547
0x9c4ec  ldarg.0
0x9c4ed  ldarg.1
0x9c4ee  ldstr    aUpdate// "Update"
0x9c4f3  ldarg.0
0x9c4f4  callvirt instance string System.Web.UI.WebControls.CommandField::get_UpdateText()
0x9c4f9  ldloc.s  6
0x9c4fb  ldloc.s  7
0x9c4fd  ldarg.s  4
0x9c4ff  ldarg.0
0x9c500  callvirt instance string System.Web.UI.WebControls.CommandField::get_UpdateImageUrl()
0x9c505  call     instance void System.Web.UI.WebControls.CommandField::AddButtonToCell(class System.Web.UI.WebControls.DataControlFieldCell cell, string commandName, string buttonText, bool causesValidation, string validationGroup, int32 rowIndex, string imageUrl)
0x9c50a  ldloc.s  4
0x9c50c  brfalse.s loc_9C547
0x9c50e  ldstr    aNbsp// "&nbsp;"
0x9c513  newobj   instance void System.Web.UI.LiteralControl::.ctor(string text)
0x9c518  stloc.s  8
0x9c51a  ldarg.1
0x9c51b  callvirt instance class System.Web.UI.ControlCollection System.Web.UI.Control::get_Controls()
0x9c520  ldloc.s  8
0x9c522  callvirt instance void System.Web.UI.ControlCollection::Add(class System.Web.UI.Control child)
0x9c527  ldarg.0
0x9c528  ldarg.1
0x9c529  ldstr    aCancel// "Cancel"
0x9c52e  ldarg.0
0x9c52f  callvirt instance string System.Web.UI.WebControls.CommandField::get_CancelText()
0x9c534  ldc.i4.0
0x9c535  ldsfld   string [mscorlib]System.String::Empty
0x9c53a  ldarg.s  4
0x9c53c  ldarg.0
0x9c53d  callvirt instance string System.Web.UI.WebControls.CommandField::get_CancelImageUrl()
0x9c542  call     instance void System.Web.UI.WebControls.CommandField::AddButtonToCell(class System.Web.UI.WebControls.DataControlFieldCell cell, string commandName, string buttonText, bool causesValidation, string validationGroup, int32 rowIndex, string imageUrl)
0x9c547  ldarg.3
0x9c548  ldc.i4.8
0x9c549  and
0x9c54a  ldc.i4.0
0x9c54b  cgt.un
0x9c54d  ldloc.2
0x9c54e  and
0x9c54f  brfalse  loc_9C6A2
0x9c554  ldarg.0
0x9c555  ldarg.1
0x9c556  ldstr    aInsert// "Insert"
0x9c55b  ldarg.0
0x9c55c  callvirt instance string System.Web.UI.WebControls.CommandField::get_InsertText()
0x9c561  ldloc.s  6
0x9c563  ldloc.s  7
0x9c565  ldarg.s  4
0x9c567  ldarg.0
0x9c568  callvirt instance string System.Web.UI.WebControls.CommandField::get_InsertImageUrl()
0x9c56d  call     instance void System.Web.UI.WebControls.CommandField::AddButtonToCell(class System.Web.UI.WebControls.DataControlFieldCell cell, string commandName, string buttonText, bool causesValidation, string validationGroup, int32 rowIndex, string imageUrl)
0x9c572  ldloc.s  4
0x9c574  brfalse  loc_9C6A2
0x9c579  ldstr    aNbsp// "&nbsp;"
0x9c57e  newobj   instance void System.Web.UI.LiteralControl::.ctor(string text)
0x9c583  stloc.s  8
0x9c585  ldarg.1
0x9c586  callvirt instance class System.Web.UI.ControlCollection System.Web.UI.Control::get_Controls()
0x9c58b  ldloc.s  8
0x9c58d  callvirt instance void System.Web.UI.ControlCollection::Add(class System.Web.UI.Control child)
0x9c592  ldarg.0
0x9c593  ldarg.1
0x9c594  ldstr    aCancel// "Cancel"
0x9c599  ldarg.0
0x9c59a  callvirt instance string System.Web.UI.WebControls.CommandField::get_CancelText()
0x9c59f  ldc.i4.0
0x9c5a0  ldsfld   string [mscorlib]System.String::Empty
0x9c5a5  ldarg.s  4
0x9c5a7  ldarg.0
0x9c5a8  callvirt instance string System.Web.UI.WebControls.CommandField::get_CancelImageUrl()
0x9c5ad  call     instance void System.Web.UI.WebControls.CommandField::AddButtonToCell(class System.Web.UI.WebControls.DataControlFieldCell cell, string commandName, string buttonText, bool causesValidation, string validationGroup, int32 rowIndex, string imageUrl)
0x9c5b2  ret
0x9c5b3  ldloc.0
0x9c5b4  brfalse.s loc_9C5D9
0x9c5b6  ldarg.0
0x9c5b7  ldarg.1
0x9c5b8  ldstr    aEdit// "Edit"
0x9c5bd  ldarg.0
0x9c5be  callvirt instance string System.Web.UI.WebControls.CommandField::get_EditText()
0x9c5c3  ldc.i4.0
0x9c5c4  ldsfld   string [mscorlib]System.String::Empty
0x9c5c9  ldarg.s  4
0x9c5cb  ldarg.0
0x9c5cc  callvirt instance string System.Web.UI.WebControls.CommandField::get_EditImageUrl()
0x9c5d1  call     instance void System.Web.UI.WebControls.CommandField::AddButtonToCell(class System.Web.UI.WebControls.DataControlFieldCell cell, string commandName, string buttonText, bool causesValidation, string validationGroup, int32 rowIndex, string imageUrl)
0x9c5d6  ldc.i4.0
0x9c5d7  stloc.s  5
0x9c5d9  ldloc.1
0x9c5da  brfalse.s loc_9C61C
0x9c5dc  ldloc.s  5
0x9c5de  brtrue.s loc_9C5F9
0x9c5e0  ldstr    aNbsp// "&nbsp;"
0x9c5e5  newobj   instance void System.Web.UI.LiteralControl::.ctor(string text)
0x9c5ea  stloc.s  8
0x9c5ec  ldarg.1
0x9c5ed  callvirt instance class System.Web.UI.ControlCollection System.Web.UI.Control::get_Controls()
0x9c5f2  ldloc.s  8
0x9c5f4  callvirt instance void System.Web.UI.ControlCollection::Add(class System.Web.UI.Control child)
0x9c5f9  ldarg.0
0x9c5fa  ldarg.1
0x9c5fb  ldstr    aDelete_1// "Delete"
0x9c600  ldarg.0
0x9c601  callvirt instance string System.Web.UI.WebControls.CommandField::get_DeleteText()
0x9c606  ldc.i4.0
0x9c607  ldsfld   string [mscorlib]System.String::Empty
0x9c60c  ldarg.s  4
0x9c60e  ldarg.0
0x9c60f  callvirt instance string System.Web.UI.WebControls.CommandField::get_DeleteImageUrl()
0x9c614  call     instance void System.Web.UI.WebControls.CommandField::AddButtonToCell(class System.Web.UI.WebControls.DataControlFieldCell cell, string commandName, string buttonText, bool causesValidation, string validationGroup, int32 rowIndex, string imageUrl)
0x9c619  ldc.i4.0
0x9c61a  stloc.s  5
0x9c61c  ldloc.2
0x9c61d  brfalse.s loc_9C65F
0x9c61f  ldloc.s  5
0x9c621  brtrue.s loc_9C63C
0x9c623  ldstr    aNbsp// "&nbsp;"
0x9c628  newobj   instance void System.Web.UI.LiteralControl::.ctor(string text)
0x9c62d  stloc.s  8
0x9c62f  ldarg.1
0x9c630  callvirt instance class System.Web.UI.ControlCollection System.Web.UI.Control::get_Controls()
0x9c635  ldloc.s  8
0x9c637  callvirt instance void System.Web.UI.ControlCollection::Add(class System.Web.UI.Control child)
0x9c63c  ldarg.0
0x9c63d  ldarg.1
0x9c63e  ldstr    aNew// "New"
0x9c643  ldarg.0
0x9c644  callvirt instance string System.Web.UI.WebControls.CommandField::get_NewText()
0x9c649  ldc.i4.0
0x9c64a  ldsfld   string [mscorlib]System.String::Empty
0x9c64f  ldarg.s  4
0x9c651  ldarg.0
0x9c652  callvirt instance string System.Web.UI.WebControls.CommandField::get_NewImageUrl()
0x9c657  call     instance void System.Web.UI.WebControls.CommandField::AddButtonToCell(class System.Web.UI.WebControls.DataControlFieldCell cell, string commandName, string buttonText, bool causesValidation, string validationGroup, int32 rowIndex, string imageUrl)
0x9c65c  ldc.i4.0
0x9c65d  stloc.s  5
0x9c65f  ldloc.3
0x9c660  brfalse.s loc_9C6A2
0x9c662  ldloc.s  5
0x9c664  brtrue.s loc_9C67F
0x9c666  ldstr    aNbsp// "&nbsp;"
0x9c66b  newobj   instance void System.Web.UI.LiteralControl::.ctor(string text)
0x9c670  stloc.s  8
0x9c672  ldarg.1
0x9c673  callvirt instance class System.Web.UI.ControlCollection System.Web.UI.Control::get_Controls()
0x9c678  ldloc.s  8
0x9c67a  callvirt instance void System.Web.UI.ControlCollection::Add(class System.Web.UI.Control child)
0x9c67f  ldarg.0
0x9c680  ldarg.1
0x9c681  ldstr    aSelect_0// "Select"
0x9c686  ldarg.0
0x9c687  callvirt instance string System.Web.UI.WebControls.CommandField::get_SelectText()
0x9c68c  ldc.i4.0
0x9c68d  ldsfld   string [mscorlib]System.String::Empty
0x9c692  ldarg.s  4
0x9c694  ldarg.0
0x9c695  callvirt instance string System.Web.UI.WebControls.CommandField::get_SelectImageUrl()
0x9c69a  call     instance void System.Web.UI.WebControls.CommandField::AddButtonToCell(class System.Web.UI.WebControls.DataControlFieldCell cell, string commandName, string buttonText, bool causesValidation, string validationGroup, int32 rowIndex, string imageUrl)
0x9c69f  ldc.i4.0
0x9c6a0  stloc.s  5
0x9c6a2  ret
```
