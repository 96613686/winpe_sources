# System.Web.UI.Design.WebControls.FormViewDesigner::AddTemplatesAndKeys

- ea: `0x242b0`
- end: `0x24a5f`
- name: `System.Web.UI.Design.WebControls.FormViewDesigner::AddTemplatesAndKeys`
- size: `1967`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x24d70`

## callees

- `0x4e90`
- `0xae10`
- `0xae20`
- `0xae60`
- `0xbe70`
- `0xbe80`
- `0xe230`
- `0xe240`
- `0xe280`
- `0xe2b0`
- `0xe350`
- `0x1bf90`
- `0x24150`
- `0x242b0`
- `0x584f0`
- `0x8ef40`

## string_xrefs

- `0x243ca`: `ReadOnly`
- `0x243f8`: `ReadOnly`
- `0x24526`: `ReadOnly`
- `0x246ff`: `<asp:LinkButton runat="server" Text="{3}" CommandName="{0}" id="{1}{0}Button" CausesValidation="{2}" />`
- `0x2478e`: `<asp:LinkButton runat="server" Text="{3}" CommandName="{0}" id="{1}{0}Button" CausesValidation="{2}" />`
- `0x247db`: `<asp:LinkButton runat="server" Text="{3}" CommandName="{0}" id="{1}{0}Button" CausesValidation="{2}" />`
- `0x24839`: `<asp:LinkButton runat="server" Text="{3}" CommandName="{0}" id="{1}{0}Button" CausesValidation="{2}" />`
- `0x2489a`: `<asp:LinkButton runat="server" Text="{3}" CommandName="{0}" id="{1}{0}Button" CausesValidation="{2}" />`
- `0x24926`: `<asp:LinkButton runat="server" Text="{3}" CommandName="{0}" id="{1}{0}Button" CausesValidation="{2}" />`
- `0x24973`: `<asp:LinkButton runat="server" Text="{3}" CommandName="{0}" id="{1}{0}Button" CausesValidation="{2}" />`
- `0x2474b`: `<asp:LinkButton runat="server" Text="{3}" CommandName="{0}" id="{1}{0}Button" CausesValidation="{2}" ValidationGroup="Insert" />`
- `0x248e3`: `<asp:LinkButton runat="server" Text="{3}" CommandName="{0}" id="{1}{0}Button" CausesValidation="{2}" ValidationGroup="Insert" />`
- `0x24758`: `Update`
- `0x2479b`: `Update`
- `0x247f0`: `Update`
- `0x24770`: `FormView_Update`
- `0x247b3`: `FormView_Update`
- `0x24846`: `Delete`
- `0x2485e`: `FormView_Delete`

## pseudocode

```c

```

## disassembly

```asm
0x242b0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x242b5  stloc.0
0x242b6  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x242bb  stloc.1
0x242bc  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x242c1  stloc.2
0x242c2  ldarg.0
0x242c3  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x242c8  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x242cd  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0x242d2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x242d7  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x242dc  castclass [System]System.ComponentModel.Design.IDesignerHost
0x242e1  stloc.3
0x242e2  ldarg.1
0x242e3  brfalse  loc_24A5E
0x242e8  ldarg.1
0x242e9  callvirt instance class System.Web.UI.Design.IDataSourceFieldSchema[] System.Web.UI.Design.IDataSourceViewSchema::GetFields()
0x242ee  stloc.s  4
0x242f0  ldloc.s  4
0x242f2  brfalse  loc_24A5E
0x242f7  ldloc.s  4
0x242f9  ldlen
0x242fa  brfalse  loc_24A5E
0x242ff  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x24304  stloc.s  5
0x24306  ldloc.s  4
0x24308  stloc.s  8
0x2430a  ldc.i4.0
0x2430b  stloc.s  9
0x2430d  br       loc_246DE
0x24312  ldloc.s  8
0x24314  ldloc.s  9
0x24316  ldelem.ref
0x24317  stloc.s  0xA
0x24319  ldloc.s  0xA
0x2431b  callvirt instance string System.Web.UI.Design.IDataSourceFieldSchema::get_Name()
0x24320  stloc.s  0xB
0x24322  ldloc.s  0xB
0x24324  callvirt instance int32 [mscorlib]System.String::get_Length()
0x24329  newarr   [mscorlib]System.Char
0x2432e  stloc.s  0xC
0x24330  ldc.i4.0
0x24331  stloc.s  0x10
0x24333  br.s     loc_24365
0x24335  ldloc.s  0xB
0x24337  ldloc.s  0x10
0x24339  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2433e  stloc.s  0x11
0x24340  ldloc.s  0x11
0x24342  call     bool [mscorlib]System.Char::IsLetterOrDigit(char)
0x24347  brtrue.s loc_2434F
0x24349  ldloc.s  0x11
0x2434b  ldc.i4.s 0x5F
0x2434d  bne.un.s loc_24358
0x2434f  ldloc.s  0xC
0x24351  ldloc.s  0x10
0x24353  ldloc.s  0x11
0x24355  stelem.i2
0x24356  br.s     loc_2435F
0x24358  ldloc.s  0xC
0x2435a  ldloc.s  0x10
0x2435c  ldc.i4.s 0x5F
0x2435e  stelem.i2
0x2435f  ldloc.s  0x10
0x24361  ldc.i4.1
0x24362  add
0x24363  stloc.s  0x10
0x24365  ldloc.s  0x10
0x24367  ldloc.s  0xB
0x24369  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2436e  blt.s    loc_24335
0x24370  ldloc.s  0xC
0x24372  newobj   instance void [mscorlib]System.String::.ctor(char[])
0x24377  stloc.s  0xD
0x24379  ldloc.s  0xB
0x2437b  ldsfld   string [mscorlib]System.String::Empty
0x24380  call     string System.Web.UI.Design.DesignTimeDataBinding::CreateEvalExpression(string field, string format)
0x24385  stloc.s  0xE
0x24387  ldloc.s  0xB
0x24389  ldsfld   string [mscorlib]System.String::Empty
0x2438e  call     string System.Web.UI.Design.DesignTimeDataBinding::CreateBindExpression(string field, string format)
0x24393  stloc.s  0xF
0x24395  ldloc.s  0xA
0x24397  callvirt instance bool System.Web.UI.Design.IDataSourceFieldSchema::get_PrimaryKey()
0x2439c  brtrue.s loc_243AA
0x2439e  ldloc.s  0xA
0x243a0  callvirt instance bool System.Web.UI.Design.IDataSourceFieldSchema::get_Identity()
0x243a5  brfalse  loc_244D5
0x243aa  ldarg.0
0x243ab  call     instance bool System.Web.UI.Design.WebControls.FormViewDesigner::get_EnableDynamicData()
0x243b0  brfalse.s loc_24410
0x243b2  ldloc.0
0x243b3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x243b8  ldstr    a0AspDynamiccon// "{0}: <asp:DynamicControl DataField=\"{0"...
0x243bd  ldc.i4.3
0x243be  newarr   [mscorlib]System.Object
0x243c3  dup
0x243c4  ldc.i4.0
0x243c5  ldloc.s  0xB
0x243c7  stelem.ref
0x243c8  dup
0x243c9  ldc.i4.1
0x243ca  ldstr    aReadonly// "ReadOnly"
0x243cf  stelem.ref
0x243d0  dup
0x243d1  ldc.i4.2
0x243d2  ldloc.s  0xD
0x243d4  stelem.ref
0x243d5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x243da  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x243df  pop
0x243e0  ldloc.1
0x243e1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x243e6  ldstr    a0AspDynamiccon// "{0}: <asp:DynamicControl DataField=\"{0"...
0x243eb  ldc.i4.3
0x243ec  newarr   [mscorlib]System.Object
0x243f1  dup
0x243f2  ldc.i4.0
0x243f3  ldloc.s  0xB
0x243f5  stelem.ref
0x243f6  dup
0x243f7  ldc.i4.1
0x243f8  ldstr    aReadonly// "ReadOnly"
0x243fd  stelem.ref
0x243fe  dup
0x243ff  ldc.i4.2
0x24400  ldloc.s  0xD
0x24402  stelem.ref
0x24403  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24408  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2440d  pop
0x2440e  br.s     loc_24466
0x24410  ldloc.0
0x24411  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24416  ldstr    a0AspLabelText1_0// "{0}: <asp:Label Text='<%# {1} %>' runat"...
0x2441b  ldc.i4.3
0x2441c  newarr   [mscorlib]System.Object
0x24421  dup
0x24422  ldc.i4.0
0x24423  ldloc.s  0xB
0x24425  stelem.ref
0x24426  dup
0x24427  ldc.i4.1
0x24428  ldloc.s  0xE
0x2442a  stelem.ref
0x2442b  dup
0x2442c  ldc.i4.2
0x2442d  ldloc.s  0xD
0x2442f  stelem.ref
0x24430  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24435  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2443a  pop
0x2443b  ldloc.1
0x2443c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24441  ldstr    a0AspLabelText1_1// "{0}: <asp:Label Text='<%# {1} %>' runat"...
0x24446  ldc.i4.3
0x24447  newarr   [mscorlib]System.Object
0x2444c  dup
0x2444d  ldc.i4.0
0x2444e  ldloc.s  0xB
0x24450  stelem.ref
0x24451  dup
0x24452  ldc.i4.1
0x24453  ldloc.s  0xE
0x24455  stelem.ref
0x24456  dup
0x24457  ldc.i4.2
0x24458  ldloc.s  0xD
0x2445a  stelem.ref
0x2445b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24460  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x24465  pop
0x24466  ldloc.s  0xA
0x24468  callvirt instance bool System.Web.UI.Design.IDataSourceFieldSchema::get_Identity()
0x2446d  brtrue   loc_246A1
0x24472  ldarg.0
0x24473  call     instance bool System.Web.UI.Design.WebControls.FormViewDesigner::get_EnableDynamicData()
0x24478  brfalse.s loc_244A5
0x2447a  ldloc.2
0x2447b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24480  ldstr    a0AspDynamiccon_0// "{0}: <asp:DynamicControl DataField=\"{0"...
0x24485  ldc.i4.2
0x24486  newarr   [mscorlib]System.Object
0x2448b  dup
0x2448c  ldc.i4.0
0x2448d  ldloc.s  0xB
0x2448f  stelem.ref
0x24490  dup
0x24491  ldc.i4.1
0x24492  ldloc.s  0xD
0x24494  stelem.ref
0x24495  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2449a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2449f  pop
0x244a0  br       loc_246A1
0x244a5  ldloc.2
0x244a6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x244ab  ldstr    a0AspTextboxTex// "{0}: <asp:TextBox Text='<%# {1} %>' run"...
0x244b0  ldc.i4.3
0x244b1  newarr   [mscorlib]System.Object
0x244b6  dup
0x244b7  ldc.i4.0
0x244b8  ldloc.s  0xB
0x244ba  stelem.ref
0x244bb  dup
0x244bc  ldc.i4.1
0x244bd  ldloc.s  0xF
0x244bf  stelem.ref
0x244c0  dup
0x244c1  ldc.i4.2
0x244c2  ldloc.s  0xD
0x244c4  stelem.ref
0x244c5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x244ca  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x244cf  pop
0x244d0  br       loc_246A1
0x244d5  ldarg.0
0x244d6  call     instance bool System.Web.UI.Design.WebControls.FormViewDesigner::get_EnableDynamicData()
0x244db  brfalse  loc_24567
0x244e0  ldloc.0
0x244e1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x244e6  ldstr    a0AspDynamiccon// "{0}: <asp:DynamicControl DataField=\"{0"...
0x244eb  ldc.i4.3
0x244ec  newarr   [mscorlib]System.Object
0x244f1  dup
0x244f2  ldc.i4.0
0x244f3  ldloc.s  0xB
0x244f5  stelem.ref
0x244f6  dup
0x244f7  ldc.i4.1
0x244f8  ldstr    aEdit// "Edit"
0x244fd  stelem.ref
0x244fe  dup
0x244ff  ldc.i4.2
0x24500  ldloc.s  0xD
0x24502  stelem.ref
0x24503  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24508  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2450d  pop
0x2450e  ldloc.1
0x2450f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24514  ldstr    a0AspDynamiccon// "{0}: <asp:DynamicControl DataField=\"{0"...
0x24519  ldc.i4.3
0x2451a  newarr   [mscorlib]System.Object
0x2451f  dup
0x24520  ldc.i4.0
0x24521  ldloc.s  0xB
0x24523  stelem.ref
0x24524  dup
0x24525  ldc.i4.1
0x24526  ldstr    aReadonly// "ReadOnly"
0x2452b  stelem.ref
0x2452c  dup
0x2452d  ldc.i4.2
0x2452e  ldloc.s  0xD
0x24530  stelem.ref
0x24531  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24536  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2453b  pop
0x2453c  ldloc.2
0x2453d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24542  ldstr    a0AspDynamiccon_0// "{0}: <asp:DynamicControl DataField=\"{0"...
0x24547  ldc.i4.2
0x24548  newarr   [mscorlib]System.Object
0x2454d  dup
0x2454e  ldc.i4.0
0x2454f  ldloc.s  0xB
0x24551  stelem.ref
0x24552  dup
0x24553  ldc.i4.1
0x24554  ldloc.s  0xD
0x24556  stelem.ref
0x24557  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2455c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x24561  pop
0x24562  br       loc_246A1
0x24567  ldloc.s  0xA
0x24569  callvirt instance class [mscorlib]System.Type System.Web.UI.Design.IDataSourceFieldSchema::get_DataType()
0x2456e  ldtoken  [mscorlib]System.Boolean
0x24573  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x24578  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2457d  brtrue.s loc_2459A
0x2457f  ldloc.s  0xA
0x24581  callvirt instance class [mscorlib]System.Type System.Web.UI.Design.IDataSourceFieldSchema::get_DataType()
0x24586  ldtoken  valuetype [mscorlib]System.Nullable`1<bool>
0x2458b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x24590  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x24595  brfalse  loc_24620
0x2459a  ldloc.0
0x2459b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x245a0  ldstr    a0AspCheckboxCh// "{0}: <asp:CheckBox Checked='<%# {1} %>'"...
0x245a5  ldc.i4.3
0x245a6  newarr   [mscorlib]System.Object
0x245ab  dup
0x245ac  ldc.i4.0
0x245ad  ldloc.s  0xB
0x245af  stelem.ref
0x245b0  dup
0x245b1  ldc.i4.1
  ... truncated ...
```
