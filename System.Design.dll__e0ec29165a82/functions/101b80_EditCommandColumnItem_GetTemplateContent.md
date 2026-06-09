# EditCommandColumnItem::GetTemplateContent

- ea: `0x101b80`
- end: `0x101cdd`
- name: `EditCommandColumnItem::GetTemplateContent`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x101b40`

## callees

- `0x101b80`

## string_xrefs

- `0x101bf3`: ` CommandName="`
- `0x101c9f`: ` CommandName="`
- `0x101b95`: `LinkButton`
- `0x101c1c`: `Update"`

## pseudocode

```c

```

## disassembly

```asm
0x101b80  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x101b85  stloc.0
0x101b86  ldarg.0
0x101b87  ldfld    valuetype [System.Web]System.Web.UI.WebControls.ButtonColumnType EditCommandColumnItem::buttonType
0x101b8c  brfalse.s loc_101B95
0x101b8e  ldstr    aButton// "Button"
0x101b93  br.s     loc_101B9A
0x101b95  ldstr    aLinkbutton// "LinkButton"
0x101b9a  stloc.1
0x101b9b  ldloc.0
0x101b9c  ldstr    aAsp_0// "<asp:"
0x101ba1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101ba6  pop
0x101ba7  ldloc.0
0x101ba8  ldloc.1
0x101ba9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101bae  pop
0x101baf  ldloc.0
0x101bb0  ldstr    aRunatServer// " runat=\"server\""
0x101bb5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101bba  pop
0x101bbb  ldloc.0
0x101bbc  ldstr    aText_2// " Text=\""
0x101bc1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101bc6  pop
0x101bc7  ldarg.1
0x101bc8  brtrue.s loc_101BD9
0x101bca  ldloc.0
0x101bcb  ldarg.0
0x101bcc  ldfld    string EditCommandColumnItem::editText
0x101bd1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101bd6  pop
0x101bd7  br.s     loc_101BE6
0x101bd9  ldloc.0
0x101bda  ldarg.0
0x101bdb  ldfld    string EditCommandColumnItem::updateText
0x101be0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101be5  pop
0x101be6  ldloc.0
0x101be7  ldstr    asc_12DFA8// "\""
0x101bec  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101bf1  pop
0x101bf2  ldloc.0
0x101bf3  ldstr    aCommandname_0// " CommandName=\""
0x101bf8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101bfd  pop
0x101bfe  ldarg.1
0x101bff  brtrue.s loc_101C1B
0x101c01  ldloc.0
0x101c02  ldstr    aEdit_0// "Edit\""
0x101c07  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101c0c  pop
0x101c0d  ldloc.0
0x101c0e  ldstr    aCausesvalidati_3// " CausesValidation=\"false\""
0x101c13  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101c18  pop
0x101c19  br.s     loc_101C27
0x101c1b  ldloc.0
0x101c1c  ldstr    aUpdate_2// "Update\""
0x101c21  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101c26  pop
0x101c27  ldloc.0
0x101c28  ldstr    aAsp_2// "></asp:"
0x101c2d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101c32  pop
0x101c33  ldloc.0
0x101c34  ldloc.1
0x101c35  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101c3a  pop
0x101c3b  ldloc.0
0x101c3c  ldstr    asc_1307F8// ">"
0x101c41  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101c46  pop
0x101c47  ldarg.1
0x101c48  brfalse  loc_101CD6
0x101c4d  ldloc.0
0x101c4e  ldstr    aNbsp// "&nbsp;"
0x101c53  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101c58  pop
0x101c59  ldloc.0
0x101c5a  ldstr    aAsp_0// "<asp:"
0x101c5f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101c64  pop
0x101c65  ldloc.0
0x101c66  ldloc.1
0x101c67  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101c6c  pop
0x101c6d  ldloc.0
0x101c6e  ldstr    aRunatServer// " runat=\"server\""
0x101c73  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101c78  pop
0x101c79  ldloc.0
0x101c7a  ldstr    aText_2// " Text=\""
0x101c7f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101c84  pop
0x101c85  ldloc.0
0x101c86  ldarg.0
0x101c87  ldfld    string EditCommandColumnItem::cancelText
0x101c8c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101c91  pop
0x101c92  ldloc.0
0x101c93  ldstr    asc_12DFA8// "\""
0x101c98  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101c9d  pop
0x101c9e  ldloc.0
0x101c9f  ldstr    aCommandname_0// " CommandName=\""
0x101ca4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101ca9  pop
0x101caa  ldloc.0
0x101cab  ldstr    aCancel_0// "Cancel\""
0x101cb0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101cb5  pop
0x101cb6  ldloc.0
0x101cb7  ldstr    aCausesvalidati_2// " CausesValidation=\"false\"></asp:"
0x101cbc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101cc1  pop
0x101cc2  ldloc.0
0x101cc3  ldloc.1
0x101cc4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101cc9  pop
0x101cca  ldloc.0
0x101ccb  ldstr    asc_1307F8// ">"
0x101cd0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x101cd5  pop
0x101cd6  ldloc.0
0x101cd7  callvirt instance string [mscorlib]System.Object::ToString()
0x101cdc  ret
```
