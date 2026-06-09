# Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::GetFilterForCategory

- ea: `0x57f40`
- end: `0x580b7`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::GetFilterForCategory`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x58700`

## callees

- `0x19640`
- `0x19700`
- `0x53600`
- `0x53f00`
- `0x57f40`

## string_xrefs

- `0x58017`: `Task = `
- `0x58029`: `( Task = `
- `0x58056`: ` or Task = `

## pseudocode

```c

```

## disassembly

```asm
0x57f40  ldarg.0
0x57f41  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::comboCategory
0x57f46  callvirt instance class [System.Windows.Forms]System.Windows.Forms.CheckedListBox Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox::get_EmbeddedList()
0x57f4b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.CheckedListBox/CheckedItemCollection [System.Windows.Forms]System.Windows.Forms.CheckedListBox::get_CheckedItems()
0x57f50  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.CheckedListBox/CheckedItemCollection::get_Count()
0x57f55  ldc.i4.0
0x57f56  ble      loc_580B5
0x57f5b  ldarg.0
0x57f5c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::comboCategory
0x57f61  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox::get_AllItemsSelected()
0x57f66  brtrue   loc_580B5
0x57f6b  ldc.i4.1
0x57f6c  stloc.1
0x57f6d  ldarg.0
0x57f6e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::comboCategory
0x57f73  callvirt instance class [System.Windows.Forms]System.Windows.Forms.CheckedListBox Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox::get_EmbeddedList()
0x57f78  callvirt instance class [System.Windows.Forms]System.Windows.Forms.CheckedListBox/CheckedItemCollection [System.Windows.Forms]System.Windows.Forms.CheckedListBox::get_CheckedItems()
0x57f7d  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.CheckedListBox/CheckedItemCollection::get_Count()
0x57f82  stloc.2
0x57f83  ldc.i4.0
0x57f84  stloc.3
0x57f85  ldsfld   string [mscorlib]System.String::Empty
0x57f8a  stloc.s  4
0x57f8c  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x57f91  stloc.s  5
0x57f93  ldarg.0
0x57f94  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::comboCategory
0x57f99  callvirt instance class [System.Windows.Forms]System.Windows.Forms.CheckedListBox Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox::get_EmbeddedList()
0x57f9e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.CheckedListBox/CheckedItemCollection [System.Windows.Forms]System.Windows.Forms.CheckedListBox::get_CheckedItems()
0x57fa3  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Windows.Forms]System.Windows.Forms.CheckedListBox/CheckedItemCollection::GetEnumerator()
0x57fa8  stloc.s  6
0x57faa  br       loc_58065
0x57faf  ldloc.s  6
0x57fb1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x57fb6  isinst   Microsoft.Windows.ManagementUI.CombinedControls.RenderValue
0x57fbb  stloc.0
0x57fbc  ldloc.0
0x57fbd  brfalse  loc_58065
0x57fc2  ldloc.0
0x57fc3  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.RenderValue::get_Value()
0x57fc8  stloc.s  7
0x57fca  ldloca.s 7
0x57fcc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x57fd1  ldtoken  [mscorlib]System.Int32
0x57fd6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x57fdb  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x57fe0  castclass [mscorlib]System.IFormatProvider
0x57fe5  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x57fea  stloc.s  4
0x57fec  ldloc.1
0x57fed  brfalse.s loc_5803C
0x57fef  ldarg.1
0x57ff0  ldind.ref
0x57ff1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x57ff6  brtrue.s loc_58006
0x57ff8  ldarg.1
0x57ff9  ldarg.1
0x57ffa  ldind.ref
0x57ffb  ldstr    aAnd// " and "
0x58000  call     string [mscorlib]System.String::Concat(string, string)
0x58005  stind.ref
0x58006  ldloc.s  5
0x58008  ldloc.s  4
0x5800a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5800f  pop
0x58010  ldloc.2
0x58011  ldc.i4.1
0x58012  bne.un.s loc_58026
0x58014  ldarg.1
0x58015  ldarg.1
0x58016  ldind.ref
0x58017  ldstr    aTask_0// "Task = "
0x5801c  ldloc.s  4
0x5801e  call     string [mscorlib]System.String::Concat(string, string, string)
0x58023  stind.ref
0x58024  br.s     loc_58038
0x58026  ldarg.1
0x58027  ldarg.1
0x58028  ldind.ref
0x58029  ldstr    aTask_1// "( Task = "
0x5802e  ldloc.s  4
0x58030  call     string [mscorlib]System.String::Concat(string, string, string)
0x58035  stind.ref
0x58036  ldc.i4.1
0x58037  stloc.3
0x58038  ldc.i4.0
0x58039  stloc.1
0x5803a  br.s     loc_58065
0x5803c  ldloc.s  5
0x5803e  ldstr    asc_AC604// ","
0x58043  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58048  pop
0x58049  ldloc.s  5
0x5804b  ldloc.s  4
0x5804d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x58052  pop
0x58053  ldarg.1
0x58054  ldarg.1
0x58055  ldind.ref
0x58056  ldstr    aOrTask// " or Task = "
0x5805b  ldloc.s  4
0x5805d  call     string [mscorlib]System.String::Concat(string, string, string)
0x58062  stind.ref
0x58063  ldc.i4.1
0x58064  stloc.3
0x58065  ldloc.s  6
0x58067  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5806c  brtrue   loc_57FAF
0x58071  leave.s  loc_58088
0x58073  ldloc.s  6
0x58075  isinst   [mscorlib]System.IDisposable
0x5807a  stloc.s  8
0x5807c  ldloc.s  8
0x5807e  brfalse.s loc_58087
0x58080  ldloc.s  8
0x58082  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x58087  endfinally
0x58088  ldloc.3
0x58089  brfalse.s loc_58099
0x5808b  ldarg.1
0x5808c  ldarg.1
0x5808d  ldind.ref
0x5808e  ldstr    asc_B534E// " )"
0x58093  call     string [mscorlib]System.String::Concat(string, string)
0x58098  stind.ref
0x58099  ldarg.0
0x5809a  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::isUserQuery
0x5809f  brtrue.s loc_580B5
0x580a1  ldarg.2
0x580a2  ldind.ref
0x580a3  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::Task
0x580a8  ldloc.s  5
0x580aa  callvirt instance string [mscorlib]System.Object::ToString()
0x580af  ldc.i4.1
0x580b0  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::SetProperty(string propertyName, string value, bool simple)
0x580b5  ldc.i4.1
0x580b6  ret
```
