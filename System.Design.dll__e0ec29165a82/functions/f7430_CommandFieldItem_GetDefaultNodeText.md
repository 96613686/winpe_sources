# CommandFieldItem::GetDefaultNodeText

- ea: `0xf7430`
- end: `0xf74f3`
- name: `CommandFieldItem::GetDefaultNodeText`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x8ef40`
- `0xf6780`
- `0xf7430`

## string_xrefs

- `0xf7487`: `DCFEditor_Node_Delete`
- `0xf74e8`: `DCFEditor_Node_Command`

## pseudocode

```c

```

## disassembly

```asm
0xf7430  ldarg.0
0xf7431  call     instance class [System.Web]System.Web.UI.WebControls.DataControlField FieldItem::get_RuntimeField()
0xf7436  castclass [System.Web]System.Web.UI.WebControls.CommandField
0xf743b  stloc.0
0xf743c  ldloc.0
0xf743d  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowEditButton()
0xf7442  brfalse.s loc_F7467
0xf7444  ldloc.0
0xf7445  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowDeleteButton()
0xf744a  brtrue.s loc_F7467
0xf744c  ldloc.0
0xf744d  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowSelectButton()
0xf7452  brtrue.s loc_F7467
0xf7454  ldloc.0
0xf7455  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowInsertButton()
0xf745a  brtrue.s loc_F7467
0xf745c  ldstr    aDcfeditorNodeE// "DCFEditor_Node_Edit"
0xf7461  call     string System.Design.SR::GetString(string name)
0xf7466  ret
0xf7467  ldloc.0
0xf7468  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowDeleteButton()
0xf746d  brfalse.s loc_F7492
0xf746f  ldloc.0
0xf7470  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowEditButton()
0xf7475  brtrue.s loc_F7492
0xf7477  ldloc.0
0xf7478  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowSelectButton()
0xf747d  brtrue.s loc_F7492
0xf747f  ldloc.0
0xf7480  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowInsertButton()
0xf7485  brtrue.s loc_F7492
0xf7487  ldstr    aDcfeditorNodeD// "DCFEditor_Node_Delete"
0xf748c  call     string System.Design.SR::GetString(string name)
0xf7491  ret
0xf7492  ldloc.0
0xf7493  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowSelectButton()
0xf7498  brfalse.s loc_F74BD
0xf749a  ldloc.0
0xf749b  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowDeleteButton()
0xf74a0  brtrue.s loc_F74BD
0xf74a2  ldloc.0
0xf74a3  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowEditButton()
0xf74a8  brtrue.s loc_F74BD
0xf74aa  ldloc.0
0xf74ab  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowInsertButton()
0xf74b0  brtrue.s loc_F74BD
0xf74b2  ldstr    aDcfeditorNodeS// "DCFEditor_Node_Select"
0xf74b7  call     string System.Design.SR::GetString(string name)
0xf74bc  ret
0xf74bd  ldloc.0
0xf74be  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowInsertButton()
0xf74c3  brfalse.s loc_F74E8
0xf74c5  ldloc.0
0xf74c6  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowDeleteButton()
0xf74cb  brtrue.s loc_F74E8
0xf74cd  ldloc.0
0xf74ce  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowSelectButton()
0xf74d3  brtrue.s loc_F74E8
0xf74d5  ldloc.0
0xf74d6  callvirt instance bool [System.Web]System.Web.UI.WebControls.CommandField::get_ShowEditButton()
0xf74db  brtrue.s loc_F74E8
0xf74dd  ldstr    aDcfeditorNodeI// "DCFEditor_Node_Insert"
0xf74e2  call     string System.Design.SR::GetString(string name)
0xf74e7  ret
0xf74e8  ldstr    aDcfeditorNodeC_0// "DCFEditor_Node_Command"
0xf74ed  call     string System.Design.SR::GetString(string name)
0xf74f2  ret
```
