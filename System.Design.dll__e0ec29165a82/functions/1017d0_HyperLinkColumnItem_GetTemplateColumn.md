# HyperLinkColumnItem::GetTemplateColumn

- ea: `0x1017d0`
- end: `0x101977`
- name: `HyperLinkColumnItem::GetTemplateColumn`
- size: `423`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x101040`
- `0x101070`
- `0x1017d0`

## string_xrefs

- `0x1017df`: `<asp:HyperLink`
- `0x101957`: `></asp:HyperLink>`

## pseudocode

```c

```

## disassembly

```asm
0x1017d0  ldarg.0
0x1017d1  ldarg.1
0x1017d2  call     instance class [System.Web]System.Web.UI.WebControls.TemplateColumn ColumnItem::GetTemplateColumn(class [System.Web]System.Web.UI.WebControls.DataGrid dataGrid)
0x1017d7  stloc.0
0x1017d8  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1017dd  stloc.1
0x1017de  ldloc.1
0x1017df  ldstr    aAspHyperlink// "<asp:HyperLink"
0x1017e4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1017e9  pop
0x1017ea  ldloc.1
0x1017eb  ldstr    aRunatServer// " runat=\"server\""
0x1017f0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1017f5  pop
0x1017f6  ldarg.0
0x1017f7  ldfld    string HyperLinkColumnItem::anchorDataTextField
0x1017fc  callvirt instance int32 [mscorlib]System.String::get_Length()
0x101801  brfalse.s loc_101868
0x101803  ldloc.1
0x101804  ldstr    aTextDatabinder// " Text='<%# DataBinder.Eval(Container, "...
0x101809  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10180e  pop
0x10180f  ldloc.1
0x101810  ldarg.0
0x101811  ldfld    string HyperLinkColumnItem::anchorDataTextField
0x101816  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10181b  pop
0x10181c  ldloc.1
0x10181d  ldstr    asc_12DFA8// "\""
0x101822  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101827  pop
0x101828  ldarg.0
0x101829  ldfld    string HyperLinkColumnItem::anchorDataTextFormatString
0x10182e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x101833  brfalse.s loc_10185A
0x101835  ldloc.1
0x101836  ldstr    asc_1E4328// ", \""
0x10183b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101840  pop
0x101841  ldloc.1
0x101842  ldarg.0
0x101843  ldfld    string HyperLinkColumnItem::anchorDataTextFormatString
0x101848  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10184d  pop
0x10184e  ldloc.1
0x10184f  ldstr    asc_12DFA8// "\""
0x101854  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101859  pop
0x10185a  ldloc.1
0x10185b  ldstr    asc_1E4330// ") %>'"
0x101860  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101865  pop
0x101866  br.s     loc_10188D
0x101868  ldloc.1
0x101869  ldstr    aText_2// " Text=\""
0x10186e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101873  pop
0x101874  ldloc.1
0x101875  ldarg.0
0x101876  ldfld    string HyperLinkColumnItem::anchorText
0x10187b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101880  pop
0x101881  ldloc.1
0x101882  ldstr    asc_12DFA8// "\""
0x101887  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10188c  pop
0x10188d  ldarg.0
0x10188e  ldfld    string HyperLinkColumnItem::dataUrlField
0x101893  callvirt instance int32 [mscorlib]System.String::get_Length()
0x101898  brfalse.s loc_1018FF
0x10189a  ldloc.1
0x10189b  ldstr    aNavigateurlDat// " NavigateUrl='<%# DataBinder.Eval(Conta"...
0x1018a0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1018a5  pop
0x1018a6  ldloc.1
0x1018a7  ldarg.0
0x1018a8  ldfld    string HyperLinkColumnItem::dataUrlField
0x1018ad  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1018b2  pop
0x1018b3  ldloc.1
0x1018b4  ldstr    asc_12DFA8// "\""
0x1018b9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1018be  pop
0x1018bf  ldarg.0
0x1018c0  ldfld    string HyperLinkColumnItem::dataUrlFormatString
0x1018c5  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1018ca  brfalse.s loc_1018F1
0x1018cc  ldloc.1
0x1018cd  ldstr    asc_1E4328// ", \""
0x1018d2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1018d7  pop
0x1018d8  ldloc.1
0x1018d9  ldarg.0
0x1018da  ldfld    string HyperLinkColumnItem::dataUrlFormatString
0x1018df  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1018e4  pop
0x1018e5  ldloc.1
0x1018e6  ldstr    asc_12DFA8// "\""
0x1018eb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1018f0  pop
0x1018f1  ldloc.1
0x1018f2  ldstr    asc_1E4330// ") %>'"
0x1018f7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1018fc  pop
0x1018fd  br.s     loc_101924
0x1018ff  ldloc.1
0x101900  ldstr    aNavigateurl_1// " NavigateUrl=\""
0x101905  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10190a  pop
0x10190b  ldloc.1
0x10190c  ldarg.0
0x10190d  ldfld    string HyperLinkColumnItem::url
0x101912  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101917  pop
0x101918  ldloc.1
0x101919  ldstr    asc_12DFA8// "\""
0x10191e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101923  pop
0x101924  ldarg.0
0x101925  ldfld    string HyperLinkColumnItem::target
0x10192a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x10192f  brfalse.s loc_101956
0x101931  ldloc.1
0x101932  ldstr    aTarget// " Target=\""
0x101937  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10193c  pop
0x10193d  ldloc.1
0x10193e  ldarg.0
0x10193f  ldfld    string HyperLinkColumnItem::target
0x101944  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101949  pop
0x10194a  ldloc.1
0x10194b  ldstr    asc_12DFA8// "\""
0x101950  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101955  pop
0x101956  ldloc.1
0x101957  ldstr    aAspHyperlink_0// "></asp:HyperLink>"
0x10195c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101961  pop
0x101962  ldloc.0
0x101963  ldarg.0
0x101964  ldarg.1
0x101965  ldloc.1
0x101966  callvirt instance string [mscorlib]System.Object::ToString()
0x10196b  call     instance class [System.Web]System.Web.UI.ITemplate ColumnItem::GetTemplate(class [System.Web]System.Web.UI.WebControls.DataGrid dataGrid, string templateContent)
0x101970  callvirt instance void [System.Web]System.Web.UI.WebControls.TemplateColumn::set_ItemTemplate(class [System.Web]System.Web.UI.ITemplate)
0x101975  ldloc.0
0x101976  ret
```
