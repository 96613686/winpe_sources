# ButtonColumnItem::GetTemplateColumn

- ea: `0x1014b0`
- end: `0x1015e4`
- name: `ButtonColumnItem::GetTemplateColumn`
- size: `308`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x101040`
- `0x101070`
- `0x1014b0`

## string_xrefs

- `0x10158b`: ` CommandName="`
- `0x1014cd`: `LinkButton`

## pseudocode

```c

```

## disassembly

```asm
0x1014b0  ldarg.0
0x1014b1  ldarg.1
0x1014b2  call     instance class [System.Web]System.Web.UI.WebControls.TemplateColumn ColumnItem::GetTemplateColumn(class [System.Web]System.Web.UI.WebControls.DataGrid dataGrid)
0x1014b7  stloc.0
0x1014b8  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1014bd  stloc.1
0x1014be  ldarg.0
0x1014bf  ldfld    valuetype [System.Web]System.Web.UI.WebControls.ButtonColumnType ButtonColumnItem::buttonType
0x1014c4  brfalse.s loc_1014CD
0x1014c6  ldstr    aButton// "Button"
0x1014cb  br.s     loc_1014D2
0x1014cd  ldstr    aLinkbutton// "LinkButton"
0x1014d2  stloc.2
0x1014d3  ldloc.1
0x1014d4  ldstr    aAsp_0// "<asp:"
0x1014d9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1014de  pop
0x1014df  ldloc.1
0x1014e0  ldloc.2
0x1014e1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1014e6  pop
0x1014e7  ldloc.1
0x1014e8  ldstr    aRunatServer// " runat=\"server\""
0x1014ed  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1014f2  pop
0x1014f3  ldarg.0
0x1014f4  ldfld    string ButtonColumnItem::buttonDataTextField
0x1014f9  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1014fe  brfalse.s loc_101565
0x101500  ldloc.1
0x101501  ldstr    aTextDatabinder// " Text='<%# DataBinder.Eval(Container, "...
0x101506  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10150b  pop
0x10150c  ldloc.1
0x10150d  ldarg.0
0x10150e  ldfld    string ButtonColumnItem::buttonDataTextField
0x101513  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101518  pop
0x101519  ldloc.1
0x10151a  ldstr    asc_12DFA8// "\""
0x10151f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101524  pop
0x101525  ldarg.0
0x101526  ldfld    string ButtonColumnItem::buttonDataTextFormatString
0x10152b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x101530  brfalse.s loc_101557
0x101532  ldloc.1
0x101533  ldstr    asc_1E4328// ", \""
0x101538  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10153d  pop
0x10153e  ldloc.1
0x10153f  ldarg.0
0x101540  ldfld    string ButtonColumnItem::buttonDataTextFormatString
0x101545  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10154a  pop
0x10154b  ldloc.1
0x10154c  ldstr    asc_12DFA8// "\""
0x101551  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101556  pop
0x101557  ldloc.1
0x101558  ldstr    asc_1E4330// ") %>'"
0x10155d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101562  pop
0x101563  br.s     loc_10158A
0x101565  ldloc.1
0x101566  ldstr    aText_2// " Text=\""
0x10156b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101570  pop
0x101571  ldloc.1
0x101572  ldarg.0
0x101573  ldfld    string ButtonColumnItem::buttonText
0x101578  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10157d  pop
0x10157e  ldloc.1
0x10157f  ldstr    asc_12DFA8// "\""
0x101584  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101589  pop
0x10158a  ldloc.1
0x10158b  ldstr    aCommandname_0// " CommandName=\""
0x101590  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101595  pop
0x101596  ldloc.1
0x101597  ldarg.0
0x101598  ldfld    string ButtonColumnItem::command
0x10159d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1015a2  pop
0x1015a3  ldloc.1
0x1015a4  ldstr    asc_12DFA8// "\""
0x1015a9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1015ae  pop
0x1015af  ldloc.1
0x1015b0  ldstr    aCausesvalidati_2// " CausesValidation=\"false\"></asp:"
0x1015b5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1015ba  pop
0x1015bb  ldloc.1
0x1015bc  ldloc.2
0x1015bd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1015c2  pop
0x1015c3  ldloc.1
0x1015c4  ldstr    asc_1307F8// ">"
0x1015c9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1015ce  pop
0x1015cf  ldloc.0
0x1015d0  ldarg.0
0x1015d1  ldarg.1
0x1015d2  ldloc.1
0x1015d3  callvirt instance string [mscorlib]System.Object::ToString()
0x1015d8  call     instance class [System.Web]System.Web.UI.ITemplate ColumnItem::GetTemplate(class [System.Web]System.Web.UI.WebControls.DataGrid dataGrid, string templateContent)
0x1015dd  callvirt instance void [System.Web]System.Web.UI.WebControls.TemplateColumn::set_ItemTemplate(class [System.Web]System.Web.UI.ITemplate)
0x1015e2  ldloc.0
0x1015e3  ret
```
