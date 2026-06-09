# Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::GenerateQueryHeaderString

- ea: `0x58a80`
- end: `0x590d0`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::GenerateQueryHeaderString`
- size: `1616`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x5a920`

## callees

- `0x12ed0`
- `0x19640`
- `0x19660`
- `0x379e0`
- `0x38ca0`
- `0x535e0`
- `0x53760`
- `0x546a0`
- `0x58a00`
- `0x58a40`
- `0x58a80`

## string_xrefs

- `0x58cb4`: `Computer`

## pseudocode

```c

```

## disassembly

```asm
0x58a80  ldarg.0
0x58a81  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::isUserQuery
0x58a86  brfalse.s loc_58A93
0x58a88  ldstr    aAdvencedfilter// "AdvencedFilterHeaderString"
0x58a8d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x58a92  ret
0x58a93  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x58a98  stloc.0
0x58a99  ldarg.0
0x58a9a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TreeComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::treeComboBoxChannels
0x58a9f  callvirt instance string[] Microsoft.Windows.ManagementUI.CombinedControls.TreeComboBox::get_SelectedChannels()
0x58aa4  stloc.1
0x58aa5  ldloc.1
0x58aa6  brfalse.s loc_58B11
0x58aa8  ldloc.1
0x58aa9  ldlen
0x58aaa  brfalse.s loc_58B11
0x58aac  ldloc.0
0x58aad  callvirt instance string [mscorlib]System.Object::ToString()
0x58ab2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x58ab7  brtrue.s loc_58AC5
0x58ab9  ldloc.0
0x58aba  ldstr    asc_B5574// "; "
0x58abf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58ac4  pop
0x58ac5  ldloc.1
0x58ac6  ldlen
0x58ac7  conv.i4
0x58ac8  ldc.i4.1
0x58ac9  ble.s    loc_58AE8
0x58acb  ldloc.0
0x58acc  ldstr    aLogs// "Logs"
0x58ad1  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x58ad6  ldstr    asc_AAB4C// ": "
0x58adb  call     string [mscorlib]System.String::Concat(string, string)
0x58ae0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58ae5  pop
0x58ae6  br.s     loc_58B03
0x58ae8  ldloc.0
0x58ae9  ldstr    aChannel// "Channel"
0x58aee  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x58af3  ldstr    asc_AAB4C// ": "
0x58af8  call     string [mscorlib]System.String::Concat(string, string)
0x58afd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58b02  pop
0x58b03  ldloc.0
0x58b04  ldarg.0
0x58b05  ldloc.1
0x58b06  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::CombineAsCommaSeperated(string[] stringArray)
0x58b0b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58b10  pop
0x58b11  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x58b16  stloc.2
0x58b17  ldarg.0
0x58b18  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::chkCritical
0x58b1d  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.CheckBox::get_Checked()
0x58b22  brfalse.s loc_58B41
0x58b24  ldloc.2
0x58b25  ldarg.0
0x58b26  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::context
0x58b2b  ldc.i4.1
0x58b2c  ldstr    asc_AA3F4// ""
0x58b31  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x58b36  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::GetLevelString(int32 level, string publisher, native int eventHandle)
0x58b3b  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x58b40  pop
0x58b41  ldarg.0
0x58b42  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::chkError
0x58b47  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.CheckBox::get_Checked()
0x58b4c  brfalse.s loc_58B6B
0x58b4e  ldloc.2
0x58b4f  ldarg.0
0x58b50  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::context
0x58b55  ldc.i4.2
0x58b56  ldstr    asc_AA3F4// ""
0x58b5b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x58b60  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::GetLevelString(int32 level, string publisher, native int eventHandle)
0x58b65  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x58b6a  pop
0x58b6b  ldarg.0
0x58b6c  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::chkWarning
0x58b71  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.CheckBox::get_Checked()
0x58b76  brfalse.s loc_58B95
0x58b78  ldloc.2
0x58b79  ldarg.0
0x58b7a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::context
0x58b7f  ldc.i4.3
0x58b80  ldstr    asc_AA3F4// ""
0x58b85  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x58b8a  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::GetLevelString(int32 level, string publisher, native int eventHandle)
0x58b8f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x58b94  pop
0x58b95  ldarg.0
0x58b96  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::chkInf
0x58b9b  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.CheckBox::get_Checked()
0x58ba0  brfalse.s loc_58BBF
0x58ba2  ldloc.2
0x58ba3  ldarg.0
0x58ba4  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::context
0x58ba9  ldc.i4.4
0x58baa  ldstr    asc_AA3F4// ""
0x58baf  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x58bb4  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::GetLevelString(int32 level, string publisher, native int eventHandle)
0x58bb9  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x58bbe  pop
0x58bbf  ldarg.0
0x58bc0  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::chkVerbose
0x58bc5  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.CheckBox::get_Checked()
0x58bca  brfalse.s loc_58BE9
0x58bcc  ldloc.2
0x58bcd  ldarg.0
0x58bce  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::context
0x58bd3  ldc.i4.5
0x58bd4  ldstr    asc_AA3F4// ""
0x58bd9  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x58bde  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::GetLevelString(int32 level, string publisher, native int eventHandle)
0x58be3  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x58be8  pop
0x58be9  ldloc.2
0x58bea  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x58bef  ldc.i4.0
0x58bf0  ble.s    loc_58C5A
0x58bf2  ldloc.0
0x58bf3  callvirt instance string [mscorlib]System.Object::ToString()
0x58bf8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x58bfd  brtrue.s loc_58C0B
0x58bff  ldloc.0
0x58c00  ldstr    asc_B5574// "; "
0x58c05  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58c0a  pop
0x58c0b  ldloc.2
0x58c0c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x58c11  ldc.i4.1
0x58c12  ble.s    loc_58C31
0x58c14  ldloc.0
0x58c15  ldstr    aLevels// "Levels"
0x58c1a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x58c1f  ldstr    asc_AAB4C// ": "
0x58c24  call     string [mscorlib]System.String::Concat(string, string)
0x58c29  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58c2e  pop
0x58c2f  br.s     loc_58C4C
0x58c31  ldloc.0
0x58c32  ldstr    aLevel// "Level"
0x58c37  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x58c3c  ldstr    asc_AAB4C// ": "
0x58c41  call     string [mscorlib]System.String::Concat(string, string)
0x58c46  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58c4b  pop
0x58c4c  ldloc.0
0x58c4d  ldarg.0
0x58c4e  ldloc.2
0x58c4f  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::CombineAsCommaSeperated(class [mscorlib]System.Collections.ArrayList list)
0x58c54  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58c59  pop
0x58c5a  ldarg.0
0x58c5b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::txtComputer
0x58c60  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x58c65  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x58c6a  brtrue.s loc_58CE5
0x58c6c  ldarg.0
0x58c6d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::txtComputer
0x58c72  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x58c77  callvirt instance string [mscorlib]System.String::Trim()
0x58c7c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x58c81  brtrue.s loc_58CE5
0x58c83  ldarg.0
0x58c84  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::txtComputer
0x58c89  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x58c8e  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::AllComputerText
0x58c93  call     bool [mscorlib]System.String::Equals(string, string)
0x58c98  brtrue.s loc_58CE5
0x58c9a  ldloc.0
0x58c9b  callvirt instance string [mscorlib]System.Object::ToString()
0x58ca0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x58ca5  brtrue.s loc_58CB3
0x58ca7  ldloc.0
0x58ca8  ldstr    asc_B5574// "; "
0x58cad  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58cb2  pop
0x58cb3  ldloc.0
0x58cb4  ldstr    aComputer// "Computer"
0x58cb9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x58cbe  ldstr    asc_AAB4C// ": "
0x58cc3  call     string [mscorlib]System.String::Concat(string, string)
0x58cc8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58ccd  pop
0x58cce  ldloc.0
0x58ccf  ldarg.0
0x58cd0  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::txtComputer
0x58cd5  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x58cda  callvirt instance string [mscorlib]System.String::Trim()
0x58cdf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58ce4  pop
0x58ce5  ldarg.0
0x58ce6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::comboSources
0x58ceb  callvirt instance string[] Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox::get_AllResults()
0x58cf0  ldlen
0x58cf1  brfalse  loc_58DAD
0x58cf6  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x58cfb  stloc.3
0x58cfc  ldarg.0
0x58cfd  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::comboSources
0x58d02  callvirt instance string[] Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox::get_AllResults()
0x58d07  stloc.s  4
0x58d09  ldc.i4.0
0x58d0a  stloc.s  5
0x58d0c  br.s     loc_58D34
0x58d0e  ldloc.s  4
0x58d10  ldloc.s  5
0x58d12  ldelem.ref
0x58d13  stloc.s  6
0x58d15  ldloc.3
0x58d16  ldarg.0
0x58d17  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::context
0x58d1c  ldloc.s  6
0x58d1e  callvirt instance string [mscorlib]System.String::Trim()
0x58d23  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::GetPublisherIdentifierFromDisplayName(string sourceDisplayName)
0x58d28  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x58d2d  pop
0x58d2e  ldloc.s  5
0x58d30  ldc.i4.1
0x58d31  add
0x58d32  stloc.s  5
0x58d34  ldloc.s  5
0x58d36  ldloc.s  4
0x58d38  ldlen
0x58d39  conv.i4
0x58d3a  blt.s    loc_58D0E
0x58d3c  ldloc.3
0x58d3d  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x58d42  ldc.i4.0
0x58d43  ble.s    loc_58DAD
0x58d45  ldloc.0
0x58d46  callvirt instance string [mscorlib]System.Object::ToString()
0x58d4b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x58d50  brtrue.s loc_58D5E
0x58d52  ldloc.0
0x58d53  ldstr    asc_B5574// "; "
0x58d58  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58d5d  pop
0x58d5e  ldloc.3
0x58d5f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x58d64  ldc.i4.1
0x58d65  ble.s    loc_58D84
0x58d67  ldloc.0
0x58d68  ldstr    aSources// "Sources"
0x58d6d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x58d72  ldstr    asc_AAB4C// ": "
0x58d77  call     string [mscorlib]System.String::Concat(string, string)
0x58d7c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58d81  pop
0x58d82  br.s     loc_58D9F
0x58d84  ldloc.0
0x58d85  ldstr    aEventsource// "EventSource"
0x58d8a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x58d8f  ldstr    asc_AAB4C// ": "
0x58d94  call     string [mscorlib]System.String::Concat(string, string)
0x58d99  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58d9e  pop
0x58d9f  ldloc.0
0x58da0  ldarg.0
0x58da1  ldloc.3
0x58da2  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::CombineAsCommaSeperated(class [mscorlib]System.Collections.ArrayList list)
0x58da7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58dac  pop
0x58dad  ldarg.0
0x58dae  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::comboCategory
0x58db3  callvirt instance class [System.Windows.Forms]System.Windows.Forms.CheckedListBox Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox::get_EmbeddedList()
0x58db8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.CheckedListBox/CheckedItemCollection [System.Windows.Forms]System.Windows.Forms.CheckedListBox::get_CheckedItems()
0x58dbd  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.CheckedListBox/CheckedItemCollection::get_Count()
0x58dc2  ldc.i4.0
0x58dc3  ble      loc_58E9D
0x58dc8  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x58dcd  stloc.s  7
0x58dcf  ldarg.0
0x58dd0  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::comboCategory
0x58dd5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.CheckedListBox Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox::get_EmbeddedList()
0x58dda  callvirt instance class [System.Windows.Forms]System.Windows.Forms.CheckedListBox/CheckedItemCollection [System.Windows.Forms]System.Windows.Forms.CheckedListBox::get_CheckedItems()
0x58ddf  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Windows.Forms]System.Windows.Forms.CheckedListBox/CheckedItemCollection::GetEnumerator()
0x58de4  stloc.s  9
0x58de6  br.s     loc_58E09
0x58de8  ldloc.s  9
0x58dea  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x58def  isinst   Microsoft.Windows.ManagementUI.CombinedControls.RenderValue
0x58df4  stloc.s  8
0x58df6  ldloc.s  8
0x58df8  brfalse.s loc_58E09
0x58dfa  ldloc.s  7
0x58dfc  ldloc.s  8
0x58dfe  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.RenderValue::get_RenderedValue()
0x58e03  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x58e08  pop
0x58e09  ldloc.s  9
0x58e0b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x58e10  brtrue.s loc_58DE8
0x58e12  leave.s  loc_58E29
0x58e14  ldloc.s  9
0x58e16  isinst   [mscorlib]System.IDisposable
0x58e1b  stloc.s  0xA
  ... truncated ...
```
