# Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::InitializeComponent

- ea: `0x19060`
- end: `0x19141`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::InitializeComponent`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18b10`

## string_xrefs

- `0x19095`: `comboBoxTimeSpan.AutoCompleteCustomSource`
- `0x190a3`: `comboBoxTimeSpan.AutoCompleteCustomSource1`
- `0x190b1`: `comboBoxTimeSpan.AutoCompleteCustomSource2`
- `0x190e4`: `comboBoxTimeSpan`
- `0x19100`: `comboBoxTimeSpan`

## pseudocode

```c

```

## disassembly

```asm
0x19060  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker
0x19065  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1906a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x1906f  stloc.0
0x19070  ldarg.0
0x19071  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x19076  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::comboBoxTimeSpan
0x1907b  ldarg.0
0x1907c  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x19081  ldarg.0
0x19082  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::comboBoxTimeSpan
0x19087  callvirt instance class [System.Windows.Forms]System.Windows.Forms.AutoCompleteStringCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_AutoCompleteCustomSource()
0x1908c  ldc.i4.3
0x1908d  newarr   [mscorlib]System.String
0x19092  dup
0x19093  ldc.i4.0
0x19094  ldloc.0
0x19095  ldstr    aComboboxtimesp// "comboBoxTimeSpan.AutoCompleteCustomSour"...
0x1909a  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x1909f  stelem.ref
0x190a0  dup
0x190a1  ldc.i4.1
0x190a2  ldloc.0
0x190a3  ldstr    aComboboxtimesp_0// "comboBoxTimeSpan.AutoCompleteCustomSour"...
0x190a8  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x190ad  stelem.ref
0x190ae  dup
0x190af  ldc.i4.2
0x190b0  ldloc.0
0x190b1  ldstr    aComboboxtimesp_1// "comboBoxTimeSpan.AutoCompleteCustomSour"...
0x190b6  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x190bb  stelem.ref
0x190bc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.AutoCompleteStringCollection::AddRange(string[])
0x190c1  ldarg.0
0x190c2  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::comboBoxTimeSpan
0x190c7  ldc.i4.1
0x190c8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_AutoCompleteMode(valuetype [System.Windows.Forms]System.Windows.Forms.AutoCompleteMode)
0x190cd  ldarg.0
0x190ce  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::comboBoxTimeSpan
0x190d3  ldc.i4   0x100
0x190d8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_AutoCompleteSource(valuetype [System.Windows.Forms]System.Windows.Forms.AutoCompleteSource)
0x190dd  ldloc.0
0x190de  ldarg.0
0x190df  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::comboBoxTimeSpan
0x190e4  ldstr    aComboboxtimesp_2// "comboBoxTimeSpan"
0x190e9  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x190ee  ldarg.0
0x190ef  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::comboBoxTimeSpan
0x190f4  ldc.i4.1
0x190f5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListControl::set_FormattingEnabled(bool)
0x190fa  ldarg.0
0x190fb  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::comboBoxTimeSpan
0x19100  ldstr    aComboboxtimesp_2// "comboBoxTimeSpan"
0x19105  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1910a  ldloc.0
0x1910b  ldarg.0
0x1910c  ldstr    aThis// "$this"
0x19111  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x19116  ldarg.0
0x19117  ldc.i4.1
0x19118  call     instance void [System.Windows.Forms]System.Windows.Forms.ContainerControl::set_AutoScaleMode(valuetype [System.Windows.Forms]System.Windows.Forms.AutoScaleMode)
0x1911d  ldarg.0
0x1911e  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x19123  ldarg.0
0x19124  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::comboBoxTimeSpan
0x19129  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x1912e  ldarg.0
0x1912f  ldstr    aTimespanpicker// "TimeSpanPicker"
0x19134  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x19139  ldarg.0
0x1913a  ldc.i4.0
0x1913b  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x19140  ret
```
