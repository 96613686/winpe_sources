# CommandFieldItem::GetTemplateContent

- ea: `0xf7550`
- end: `0xf7813`
- name: `CommandFieldItem::GetTemplateContent`
- size: `707`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0xf7500`

## callees

- `0xf6780`
- `0xf7340`
- `0xf7550`

## string_xrefs

- `0xf75d8`: `Update`
- `0xf7760`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0xf7550  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xf7555  stloc.0
0xf7556  ldarg.0
0xf7557  call     instance class [System.Web]System.Web.UI.WebControls.DataControlField FieldItem::get_RuntimeField()
0xf755c  castclass [System.Web]System.Web.UI.WebControls.CommandField
0xf7561  stloc.1
0xf7562  ldtoken  [System.Web]System.Web.UI.WebControls.Button
0xf7567  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf756c  stloc.2
0xf756d  ldc.i4.1
0xf756e  stloc.3
0xf756f  ldloc.1
0xf7570  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.ButtonType [System.Web]System.Web.UI.WebControls.ButtonFieldBase::get_ButtonType()
0xf7575  ldc.i4.2
0xf7576  bne.un.s loc_F7585
0xf7578  ldtoken  [System.Web]System.Web.UI.WebControls.LinkButton
0xf757d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf7582  stloc.2
0xf7583  br.s     loc_F7599
0xf7585  ldloc.1
0xf7586  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.ButtonType [System.Web]System.Web.UI.WebControls.ButtonFieldBase::get_ButtonType()
0xf758b  ldc.i4.1
0xf758c  bne.un.s loc_F7599
0xf758e  ldtoken  [System.Web]System.Web.UI.WebControls.ImageButton
0xf7593  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf7598  stloc.2
0xf7599  ldarg.1
0xf759a  switch   loc_F7645, loc_F75B0, loc_F777F
0xf75ab  br       loc_F780C
0xf75b0  ldloc.1
0xf75b1  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowEditButton()
0xf75b6  brfalse  loc_F780C
0xf75bb  ldloc.1
0xf75bc  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.ButtonType [System.Web]System.Web.UI.WebControls.ButtonFieldBase::get_ButtonType()
0xf75c1  ldc.i4.1
0xf75c2  beq.s    loc_F75C7
0xf75c4  ldnull
0xf75c5  br.s     loc_F75CD
0xf75c7  ldloc.1
0xf75c8  callvirt instance string [System.Web]System.Web.UI.WebControls.CommandField::get_UpdateImageUrl()
0xf75cd  stloc.s  5
0xf75cf  ldloc.0
0xf75d0  ldarg.0
0xf75d1  ldloc.2
0xf75d2  ldloc.1
0xf75d3  callvirt instance string [System.Web]System.Web.UI.WebControls.CommandField::get_UpdateText()
0xf75d8  ldstr    aUpdate// "Update"
0xf75dd  ldloc.s  5
0xf75df  ldc.i4.1
0xf75e0  ldc.i4.1
0xf75e1  ldloca.s 3
0xf75e3  call     instance string CommandFieldItem::BuildButtonString(class [mscorlib]System.Type controlType, string buttonText, string commandName, string imageUrl, bool causesValidation, int32 mode, int32& buttonNameStartIndex)
0xf75e8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf75ed  pop
0xf75ee  ldloc.3
0xf75ef  ldc.i4.1
0xf75f0  add
0xf75f1  stloc.3
0xf75f2  ldloc.1
0xf75f3  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowCancelButton()
0xf75f8  brfalse  loc_F780C
0xf75fd  ldloc.0
0xf75fe  ldstr    aNbsp// "&nbsp;"
0xf7603  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf7608  pop
0xf7609  ldloc.1
0xf760a  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.ButtonType [System.Web]System.Web.UI.WebControls.ButtonFieldBase::get_ButtonType()
0xf760f  ldc.i4.1
0xf7610  beq.s    loc_F7615
0xf7612  ldnull
0xf7613  br.s     loc_F761B
0xf7615  ldloc.1
0xf7616  callvirt instance string [System.Web]System.Web.UI.WebControls.CommandField::get_CancelImageUrl()
0xf761b  stloc.s  6
0xf761d  ldloc.0
0xf761e  ldarg.0
0xf761f  ldloc.2
0xf7620  ldloc.1
0xf7621  callvirt instance string [System.Web]System.Web.UI.WebControls.CommandField::get_CancelText()
0xf7626  ldstr    aCancel// "Cancel"
0xf762b  ldloc.s  6
0xf762d  ldc.i4.0
0xf762e  ldc.i4.1
0xf762f  ldloca.s 3
0xf7631  call     instance string CommandFieldItem::BuildButtonString(class [mscorlib]System.Type controlType, string buttonText, string commandName, string imageUrl, bool causesValidation, int32 mode, int32& buttonNameStartIndex)
0xf7636  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf763b  pop
0xf763c  ldloc.3
0xf763d  ldc.i4.1
0xf763e  add
0xf763f  stloc.3
0xf7640  br       loc_F780C
0xf7645  ldc.i4.1
0xf7646  stloc.s  4
0xf7648  ldloc.1
0xf7649  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowEditButton()
0xf764e  brfalse.s loc_F768A
0xf7650  ldloc.1
0xf7651  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.ButtonType [System.Web]System.Web.UI.WebControls.ButtonFieldBase::get_ButtonType()
0xf7656  ldc.i4.1
0xf7657  beq.s    loc_F765C
0xf7659  ldnull
0xf765a  br.s     loc_F7662
0xf765c  ldloc.1
0xf765d  callvirt instance string [System.Web]System.Web.UI.WebControls.CommandField::get_EditImageUrl()
0xf7662  stloc.s  7
0xf7664  ldloc.0
0xf7665  ldarg.0
0xf7666  ldloc.2
0xf7667  ldloc.1
0xf7668  callvirt instance string [System.Web]System.Web.UI.WebControls.CommandField::get_EditText()
0xf766d  ldstr    aEdit// "Edit"
0xf7672  ldloc.s  7
0xf7674  ldc.i4.0
0xf7675  ldc.i4.0
0xf7676  ldloca.s 3
0xf7678  call     instance string CommandFieldItem::BuildButtonString(class [mscorlib]System.Type controlType, string buttonText, string commandName, string imageUrl, bool causesValidation, int32 mode, int32& buttonNameStartIndex)
0xf767d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf7682  pop
0xf7683  ldloc.3
0xf7684  ldc.i4.1
0xf7685  add
0xf7686  stloc.3
0xf7687  ldc.i4.0
0xf7688  stloc.s  4
0xf768a  ldloc.1
0xf768b  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowInsertButton()
0xf7690  brfalse.s loc_F76D9
0xf7692  ldloc.s  4
0xf7694  brtrue.s loc_F76A2
0xf7696  ldloc.0
0xf7697  ldstr    aNbsp// "&nbsp;"
0xf769c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf76a1  pop
0xf76a2  ldloc.1
0xf76a3  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.ButtonType [System.Web]System.Web.UI.WebControls.ButtonFieldBase::get_ButtonType()
0xf76a8  ldc.i4.1
0xf76a9  beq.s    loc_F76AE
0xf76ab  ldnull
0xf76ac  br.s     loc_F76B4
0xf76ae  ldloc.1
0xf76af  callvirt instance string [System.Web]System.Web.UI.WebControls.CommandField::get_NewImageUrl()
0xf76b4  stloc.s  8
0xf76b6  ldloc.0
0xf76b7  ldarg.0
0xf76b8  ldloc.2
0xf76b9  ldloc.1
0xf76ba  callvirt instance string [System.Web]System.Web.UI.WebControls.CommandField::get_NewText()
0xf76bf  ldstr    aNew// "New"
0xf76c4  ldloc.s  8
0xf76c6  ldc.i4.0
0xf76c7  ldc.i4.0
0xf76c8  ldloca.s 3
0xf76ca  call     instance string CommandFieldItem::BuildButtonString(class [mscorlib]System.Type controlType, string buttonText, string commandName, string imageUrl, bool causesValidation, int32 mode, int32& buttonNameStartIndex)
0xf76cf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf76d4  pop
0xf76d5  ldloc.3
0xf76d6  ldc.i4.1
0xf76d7  add
0xf76d8  stloc.3
0xf76d9  ldloc.1
0xf76da  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowSelectButton()
0xf76df  brfalse.s loc_F7728
0xf76e1  ldloc.s  4
0xf76e3  brtrue.s loc_F76F1
0xf76e5  ldloc.0
0xf76e6  ldstr    aNbsp// "&nbsp;"
0xf76eb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf76f0  pop
0xf76f1  ldloc.1
0xf76f2  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.ButtonType [System.Web]System.Web.UI.WebControls.ButtonFieldBase::get_ButtonType()
0xf76f7  ldc.i4.1
0xf76f8  beq.s    loc_F76FD
0xf76fa  ldnull
0xf76fb  br.s     loc_F7703
0xf76fd  ldloc.1
0xf76fe  callvirt instance string [System.Web]System.Web.UI.WebControls.CommandField::get_SelectImageUrl()
0xf7703  stloc.s  9
0xf7705  ldloc.0
0xf7706  ldarg.0
0xf7707  ldloc.2
0xf7708  ldloc.1
0xf7709  callvirt instance string [System.Web]System.Web.UI.WebControls.CommandField::get_SelectText()
0xf770e  ldstr    aSelect_1// "Select"
0xf7713  ldloc.s  9
0xf7715  ldc.i4.0
0xf7716  ldc.i4.0
0xf7717  ldloca.s 3
0xf7719  call     instance string CommandFieldItem::BuildButtonString(class [mscorlib]System.Type controlType, string buttonText, string commandName, string imageUrl, bool causesValidation, int32 mode, int32& buttonNameStartIndex)
0xf771e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf7723  pop
0xf7724  ldloc.3
0xf7725  ldc.i4.1
0xf7726  add
0xf7727  stloc.3
0xf7728  ldloc.1
0xf7729  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowDeleteButton()
0xf772e  brfalse  loc_F780C
0xf7733  ldloc.s  4
0xf7735  brtrue.s loc_F7743
0xf7737  ldloc.0
0xf7738  ldstr    aNbsp// "&nbsp;"
0xf773d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf7742  pop
0xf7743  ldloc.1
0xf7744  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.ButtonType [System.Web]System.Web.UI.WebControls.ButtonFieldBase::get_ButtonType()
0xf7749  ldc.i4.1
0xf774a  beq.s    loc_F774F
0xf774c  ldnull
0xf774d  br.s     loc_F7755
0xf774f  ldloc.1
0xf7750  callvirt instance string [System.Web]System.Web.UI.WebControls.CommandField::get_DeleteImageUrl()
0xf7755  stloc.s  0xA
0xf7757  ldloc.0
0xf7758  ldarg.0
0xf7759  ldloc.2
0xf775a  ldloc.1
0xf775b  callvirt instance string [System.Web]System.Web.UI.WebControls.CommandField::get_DeleteText()
0xf7760  ldstr    aDelete// "Delete"
0xf7765  ldloc.s  0xA
0xf7767  ldc.i4.0
0xf7768  ldc.i4.0
0xf7769  ldloca.s 3
0xf776b  call     instance string CommandFieldItem::BuildButtonString(class [mscorlib]System.Type controlType, string buttonText, string commandName, string imageUrl, bool causesValidation, int32 mode, int32& buttonNameStartIndex)
0xf7770  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf7775  pop
0xf7776  ldloc.3
0xf7777  ldc.i4.1
0xf7778  add
0xf7779  stloc.3
0xf777a  br       loc_F780C
0xf777f  ldloc.1
0xf7780  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowInsertButton()
0xf7785  brfalse  loc_F780C
0xf778a  ldloc.1
0xf778b  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.ButtonType [System.Web]System.Web.UI.WebControls.ButtonFieldBase::get_ButtonType()
0xf7790  ldc.i4.1
0xf7791  beq.s    loc_F7796
0xf7793  ldnull
0xf7794  br.s     loc_F779C
0xf7796  ldloc.1
0xf7797  callvirt instance string [System.Web]System.Web.UI.WebControls.CommandField::get_InsertImageUrl()
0xf779c  stloc.s  0xB
0xf779e  ldloc.0
0xf779f  ldarg.0
0xf77a0  ldloc.2
0xf77a1  ldloc.1
0xf77a2  callvirt instance string [System.Web]System.Web.UI.WebControls.CommandField::get_InsertText()
0xf77a7  ldstr    aInsert// "Insert"
0xf77ac  ldloc.s  0xB
0xf77ae  ldc.i4.1
0xf77af  ldc.i4.2
0xf77b0  ldloca.s 3
0xf77b2  call     instance string CommandFieldItem::BuildButtonString(class [mscorlib]System.Type controlType, string buttonText, string commandName, string imageUrl, bool causesValidation, int32 mode, int32& buttonNameStartIndex)
0xf77b7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf77bc  pop
0xf77bd  ldloc.3
0xf77be  ldc.i4.1
0xf77bf  add
0xf77c0  stloc.3
0xf77c1  ldloc.1
0xf77c2  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowCancelButton()
0xf77c7  brfalse.s loc_F780C
0xf77c9  ldloc.0
0xf77ca  ldstr    aNbsp// "&nbsp;"
0xf77cf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf77d4  pop
0xf77d5  ldloc.1
0xf77d6  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.ButtonType [System.Web]System.Web.UI.WebControls.ButtonFieldBase::get_ButtonType()
0xf77db  ldc.i4.1
0xf77dc  beq.s    loc_F77E1
0xf77de  ldnull
0xf77df  br.s     loc_F77E7
0xf77e1  ldloc.1
0xf77e2  callvirt instance string [System.Web]System.Web.UI.WebControls.CommandField::get_CancelImageUrl()
0xf77e7  stloc.s  0xC
0xf77e9  ldloc.0
0xf77ea  ldarg.0
0xf77eb  ldloc.2
0xf77ec  ldloc.1
0xf77ed  callvirt instance string [System.Web]System.Web.UI.WebControls.CommandField::get_CancelText()
0xf77f2  ldstr    aCancel// "Cancel"
0xf77f7  ldloc.s  0xC
0xf77f9  ldc.i4.0
0xf77fa  ldc.i4.2
0xf77fb  ldloca.s 3
0xf77fd  call     instance string CommandFieldItem::BuildButtonString(class [mscorlib]System.Type controlType, string buttonText, string commandName, string imageUrl, bool causesValidation, int32 mode, int32& buttonNameStartIndex)
0xf7802  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xf7807  pop
0xf7808  ldloc.3
0xf7809  ldc.i4.1
0xf780a  add
0xf780b  stloc.3
0xf780c  ldloc.0
0xf780d  callvirt instance string [mscorlib]System.Object::ToString()
0xf7812  ret
```
