# System.Windows.SystemResourceKey::GetSystemResourceKey

- ea: `0x2a9f0`
- end: `0x2ad48`
- name: `System.Windows.SystemResourceKey::GetSystemResourceKey`
- size: `856`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x207a70`

## callees

- `0x27b50`
- `0x27b70`
- `0x27b90`
- `0x2a9f0`
- `0x2ae00`
- `0x2ae30`
- `0x2ae60`
- `0x2ae80`
- `0x2aeb0`
- `0x2aee0`
- `0x2af00`
- `0x2af20`
- `0x2af40`
- `0x2af60`
- `0x2af80`
- `0x2afa0`
- `0x2afc0`
- `0x2afe0`
- `0x2b000`
- `0x2b020`
- `0x2b040`
- `0x251300`

## string_xrefs

- `0x2ab31`: `SystemParameters.FocusVisualStyleKey`
- `0x2ab9a`: `ToolBar.ComboBoxStyleKey`
- `0x2ac18`: `SystemParameters.NavigationChromeStyleKey`
- `0x2ac2d`: `SystemParameters.NavigationChromeDownLevelStyleKey`
- `0x2acc0`: `DataGridComboBoxColumn.TextBlockComboBoxStyleKey`

## pseudocode

```c

```

## disassembly

```asm
0x2a9f0  ldarg.0
0x2a9f1  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x2a9f6  stloc.0
0x2a9f7  ldloc.0
0x2a9f8  ldc.i4   0x79F14F50
0x2a9fd  bgt.un   loc_2AA9C
0x2aa02  ldloc.0
0x2aa03  ldc.i4   0x2A0842E0
0x2aa08  bgt.un.s loc_2AA53
0x2aa0a  ldloc.0
0x2aa0b  ldc.i4   0x1B88CE25
0x2aa10  bgt.un.s loc_2AA2D
0x2aa12  ldloc.0
0x2aa13  ldc.i4   0x8AD0479
0x2aa18  beq      loc_2ACBF
0x2aa1d  ldloc.0
0x2aa1e  ldc.i4   0x1B88CE25
0x2aa23  beq      loc_2AC02
0x2aa28  br       loc_2AD46
0x2aa2d  ldloc.0
0x2aa2e  ldc.i4   0x1D6A24B2
0x2aa33  beq      loc_2ACAA
0x2aa38  ldloc.0
0x2aa39  ldc.i4   0x2656822D
0x2aa3e  beq      loc_2AB84
0x2aa43  ldloc.0
0x2aa44  ldc.i4   0x2A0842E0
0x2aa49  beq      loc_2ABED
0x2aa4e  br       loc_2AD46
0x2aa53  ldloc.0
0x2aa54  ldc.i4   0x4891B976
0x2aa59  bgt.un.s loc_2AA76
0x2aa5b  ldloc.0
0x2aa5c  ldc.i4   0x46599392
0x2aa61  beq      loc_2ABAE
0x2aa66  ldloc.0
0x2aa67  ldc.i4   0x4891B976
0x2aa6c  beq      loc_2AC17
0x2aa71  br       loc_2AD46
0x2aa76  ldloc.0
0x2aa77  ldc.i4   0x4A5775F1
0x2aa7c  beq      loc_2AC95
0x2aa81  ldloc.0
0x2aa82  ldc.i4   0x630FC2EE
0x2aa87  beq      loc_2AB30
0x2aa8c  ldloc.0
0x2aa8d  ldc.i4   0x79F14F50
0x2aa92  beq      loc_2AC56
0x2aa97  br       loc_2AD46
0x2aa9c  ldloc.0
0x2aa9d  ldc.i4   0xA89C1A8D
0x2aaa2  bgt.un.s loc_2AAEA
0x2aaa4  ldloc.0
0x2aaa5  ldc.i4   0x8DD441DE
0x2aaaa  bgt.un.s loc_2AAC7
0x2aaac  ldloc.0
0x2aaad  ldc.i4   0x81ADE9CF
0x2aab2  beq      loc_2AC6B
0x2aab7  ldloc.0
0x2aab8  ldc.i4   0x8DD441DE
0x2aabd  beq      loc_2AB5A
0x2aac2  br       loc_2AD46
0x2aac7  ldloc.0
0x2aac8  ldc.i4   0xA2B237AD
0x2aacd  beq      loc_2ABC3
0x2aad2  ldloc.0
0x2aad3  ldc.i4   0xA6B17026
0x2aad8  beq.s    loc_2AB45
0x2aada  ldloc.0
0x2aadb  ldc.i4   0xA89C1A8D
0x2aae0  beq      loc_2ABD8
0x2aae5  br       loc_2AD46
0x2aaea  ldloc.0
0x2aaeb  ldc.i4   0xC0665C5D
0x2aaf0  bgt.un.s loc_2AB0D
0x2aaf2  ldloc.0
0x2aaf3  ldc.i4   0xBA3F66AC
0x2aaf8  beq      loc_2AC2C
0x2aafd  ldloc.0
0x2aafe  ldc.i4   0xC0665C5D
0x2ab03  beq      loc_2AB99
0x2ab08  br       loc_2AD46
0x2ab0d  ldloc.0
0x2ab0e  ldc.i4   0xD71F0BBF
0x2ab13  beq.s    loc_2AB6F
0x2ab15  ldloc.0
0x2ab16  ldc.i4   0xE78D731F
0x2ab1b  beq      loc_2AC41
0x2ab20  ldloc.0
0x2ab21  ldc.i4   0xEA2336B9
0x2ab26  beq      loc_2AC80
0x2ab2b  br       loc_2AD46
0x2ab30  ldarg.0
0x2ab31  ldstr    aSystemparamete// "SystemParameters.FocusVisualStyleKey"
0x2ab36  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ab3b  brtrue   loc_2ACCE
0x2ab40  br       loc_2AD46
0x2ab45  ldarg.0
0x2ab46  ldstr    aToolbarButtons// "ToolBar.ButtonStyleKey"
0x2ab4b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ab50  brtrue   loc_2ACD4
0x2ab55  br       loc_2AD46
0x2ab5a  ldarg.0
0x2ab5b  ldstr    aToolbarToggleb// "ToolBar.ToggleButtonStyleKey"
0x2ab60  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ab65  brtrue   loc_2ACDA
0x2ab6a  br       loc_2AD46
0x2ab6f  ldarg.0
0x2ab70  ldstr    aToolbarCheckbo// "ToolBar.CheckBoxStyleKey"
0x2ab75  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ab7a  brtrue   loc_2ACE0
0x2ab7f  br       loc_2AD46
0x2ab84  ldarg.0
0x2ab85  ldstr    aToolbarRadiobu// "ToolBar.RadioButtonStyleKey"
0x2ab8a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ab8f  brtrue   loc_2ACE6
0x2ab94  br       loc_2AD46
0x2ab99  ldarg.0
0x2ab9a  ldstr    aToolbarCombobo// "ToolBar.ComboBoxStyleKey"
0x2ab9f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2aba4  brtrue   loc_2ACEC
0x2aba9  br       loc_2AD46
0x2abae  ldarg.0
0x2abaf  ldstr    aToolbarTextbox// "ToolBar.TextBoxStyleKey"
0x2abb4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2abb9  brtrue   loc_2ACF2
0x2abbe  br       loc_2AD46
0x2abc3  ldarg.0
0x2abc4  ldstr    aToolbarMenusty// "ToolBar.MenuStyleKey"
0x2abc9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2abce  brtrue   loc_2ACF8
0x2abd3  br       loc_2AD46
0x2abd8  ldarg.0
0x2abd9  ldstr    aToolbarSeparat// "ToolBar.SeparatorStyleKey"
0x2abde  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2abe3  brtrue   loc_2ACFE
0x2abe8  br       loc_2AD46
0x2abed  ldarg.0
0x2abee  ldstr    aMenuitemSepara// "MenuItem.SeparatorStyleKey"
0x2abf3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2abf8  brtrue   loc_2AD04
0x2abfd  br       loc_2AD46
0x2ac02  ldarg.0
0x2ac03  ldstr    aStatusbarSepar// "StatusBar.SeparatorStyleKey"
0x2ac08  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ac0d  brtrue   loc_2AD0A
0x2ac12  br       loc_2AD46
0x2ac17  ldarg.0
0x2ac18  ldstr    aSystemparamete_0// "SystemParameters.NavigationChromeStyleK"...
0x2ac1d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ac22  brtrue   loc_2AD10
0x2ac27  br       loc_2AD46
0x2ac2c  ldarg.0
0x2ac2d  ldstr    aSystemparamete_1// "SystemParameters.NavigationChromeDownLe"...
0x2ac32  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ac37  brtrue   loc_2AD16
0x2ac3c  br       loc_2AD46
0x2ac41  ldarg.0
0x2ac42  ldstr    aGridviewGridvi// "GridView.GridViewStyleKey"
0x2ac47  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ac4c  brtrue   loc_2AD1C
0x2ac51  br       loc_2AD46
0x2ac56  ldarg.0
0x2ac57  ldstr    aGridviewGridvi_0// "GridView.GridViewScrollViewerStyleKey"
0x2ac5c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ac61  brtrue   loc_2AD22
0x2ac66  br       loc_2AD46
0x2ac6b  ldarg.0
0x2ac6c  ldstr    aGridviewGridvi_1// "GridView.GridViewItemContainerStyleKey"
0x2ac71  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ac76  brtrue   loc_2AD28
0x2ac7b  br       loc_2AD46
0x2ac80  ldarg.0
0x2ac81  ldstr    aDatagridcolumn// "DataGridColumnHeader.ColumnFloatingHead"...
0x2ac86  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ac8b  brtrue   loc_2AD2E
0x2ac90  br       loc_2AD46
0x2ac95  ldarg.0
0x2ac96  ldstr    aDatagridcolumn_0// "DataGridColumnHeader.ColumnHeaderDropSe"...
0x2ac9b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2aca0  brtrue   loc_2AD34
0x2aca5  br       loc_2AD46
0x2acaa  ldarg.0
0x2acab  ldstr    aDatagridFocusb// "DataGrid.FocusBorderBrushKey"
0x2acb0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2acb5  brtrue   loc_2AD3A
0x2acba  br       loc_2AD46
0x2acbf  ldarg.0
0x2acc0  ldstr    aDatagridcombob// "DataGridComboBoxColumn.TextBlockComboBo"...
0x2acc5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2acca  brtrue.s loc_2AD40
0x2accc  br.s     loc_2AD46
0x2acce  call     class System.Windows.ResourceKey System.Windows.SystemParameters::get_FocusVisualStyleKey()
0x2acd3  ret
0x2acd4  call     class System.Windows.ResourceKey System.Windows.SystemResourceKey::get_ToolBarButtonStyleKey()
0x2acd9  ret
0x2acda  call     class System.Windows.ResourceKey System.Windows.SystemResourceKey::get_ToolBarToggleButtonStyleKey()
0x2acdf  ret
0x2ace0  call     class System.Windows.ResourceKey System.Windows.SystemResourceKey::get_ToolBarCheckBoxStyleKey()
0x2ace5  ret
0x2ace6  call     class System.Windows.ResourceKey System.Windows.SystemResourceKey::get_ToolBarRadioButtonStyleKey()
0x2aceb  ret
0x2acec  call     class System.Windows.ResourceKey System.Windows.SystemResourceKey::get_ToolBarComboBoxStyleKey()
0x2acf1  ret
0x2acf2  call     class System.Windows.ResourceKey System.Windows.SystemResourceKey::get_ToolBarTextBoxStyleKey()
0x2acf7  ret
0x2acf8  call     class System.Windows.ResourceKey System.Windows.SystemResourceKey::get_ToolBarMenuStyleKey()
0x2acfd  ret
0x2acfe  call     class System.Windows.ResourceKey System.Windows.SystemResourceKey::get_ToolBarSeparatorStyleKey()
0x2ad03  ret
0x2ad04  call     class System.Windows.ResourceKey System.Windows.SystemResourceKey::get_MenuItemSeparatorStyleKey()
0x2ad09  ret
0x2ad0a  call     class System.Windows.ResourceKey System.Windows.SystemResourceKey::get_StatusBarSeparatorStyleKey()
0x2ad0f  ret
0x2ad10  call     class System.Windows.ResourceKey System.Windows.SystemParameters::get_NavigationChromeStyleKey()
0x2ad15  ret
0x2ad16  call     class System.Windows.ResourceKey System.Windows.SystemParameters::get_NavigationChromeDownLevelStyleKey()
0x2ad1b  ret
0x2ad1c  call     class System.Windows.ResourceKey System.Windows.SystemResourceKey::get_GridViewStyleKey()
0x2ad21  ret
0x2ad22  call     class System.Windows.ResourceKey System.Windows.SystemResourceKey::get_GridViewScrollViewerStyleKey()
0x2ad27  ret
0x2ad28  call     class System.Windows.ResourceKey System.Windows.SystemResourceKey::get_GridViewItemContainerStyleKey()
0x2ad2d  ret
0x2ad2e  call     class System.Windows.ComponentResourceKey System.Windows.SystemResourceKey::get_DataGridColumnHeaderColumnFloatingHeaderStyleKey()
0x2ad33  ret
0x2ad34  call     class System.Windows.ComponentResourceKey System.Windows.SystemResourceKey::get_DataGridColumnHeaderColumnHeaderDropSeparatorStyleKey()
0x2ad39  ret
0x2ad3a  call     class System.Windows.ComponentResourceKey System.Windows.SystemResourceKey::get_DataGridFocusBorderBrushKey()
0x2ad3f  ret
0x2ad40  call     class System.Windows.ComponentResourceKey System.Windows.SystemResourceKey::get_DataGridComboBoxColumnTextBlockComboBoxStyleKey()
0x2ad45  ret
0x2ad46  ldnull
0x2ad47  ret
```
