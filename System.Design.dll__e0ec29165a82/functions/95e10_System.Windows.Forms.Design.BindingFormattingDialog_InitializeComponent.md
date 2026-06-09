# System.Windows.Forms.Design.BindingFormattingDialog::InitializeComponent

- ea: `0x95e10`
- end: `0x964de`
- name: `System.Windows.Forms.Design.BindingFormattingDialog::InitializeComponent`
- size: `1742`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x95640`

## callees

- `0x96ab0`
- `0x96f40`
- `0xb6f70`
- `0xb70c0`
- `0x113f30`

## string_xrefs

- `0x961c7`: `updateModeLabel`
- `0x961d7`: `updateModeLabel`
- `0x961f4`: `bindingUpdateDropDown`
- `0x96210`: `bindingUpdateDropDown`

## pseudocode

```c

```

## disassembly

```asm
0x95e10  ldtoken  System.Windows.Forms.Design.BindingFormattingDialog
0x95e15  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x95e1a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x95e1f  stloc.0
0x95e20  ldarg.0
0x95e21  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x95e26  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.BindingFormattingDialog::explanationLabel
0x95e2b  ldarg.0
0x95e2c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x95e31  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x95e36  ldarg.0
0x95e37  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TreeView::.ctor()
0x95e3c  stfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Windows.Forms.Design.BindingFormattingDialog::propertiesTreeView
0x95e41  ldarg.0
0x95e42  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x95e47  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.BindingFormattingDialog::propertyLabel
0x95e4c  ldarg.0
0x95e4d  newobj   instance void System.Windows.Forms.Design.BindingFormattingWindowsFormsEditorService::.ctor()
0x95e52  stfld    class System.Windows.Forms.Design.BindingFormattingWindowsFormsEditorService System.Windows.Forms.Design.BindingFormattingDialog::dataSourcePicker
0x95e57  ldarg.0
0x95e58  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x95e5d  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.BindingFormattingDialog::bindingLabel
0x95e62  ldarg.0
0x95e63  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x95e68  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.BindingFormattingDialog::updateModeLabel
0x95e6d  ldarg.0
0x95e6e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x95e73  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox System.Windows.Forms.Design.BindingFormattingDialog::bindingUpdateDropDown
0x95e78  ldarg.0
0x95e79  newobj   instance void System.Windows.Forms.Design.FormatControl::.ctor()
0x95e7e  stfld    class System.Windows.Forms.Design.FormatControl System.Windows.Forms.Design.BindingFormattingDialog::formatControl1
0x95e83  ldarg.0
0x95e84  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x95e89  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::okCancelTableLayoutPanel
0x95e8e  ldarg.0
0x95e8f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x95e94  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.BindingFormattingDialog::okButton
0x95e99  ldarg.0
0x95e9a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x95e9f  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.BindingFormattingDialog::cancelButton
0x95ea4  ldarg.0
0x95ea5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x95eaa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x95eaf  ldarg.0
0x95eb0  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::okCancelTableLayoutPanel
0x95eb5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x95eba  ldarg.0
0x95ebb  ldc.i4.0
0x95ebc  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_ShowIcon(bool)
0x95ec1  ldarg.0
0x95ec2  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x95ec7  ldloc.0
0x95ec8  ldarg.0
0x95ec9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.BindingFormattingDialog::explanationLabel
0x95ece  ldstr    aExplanationlab// "explanationLabel"
0x95ed3  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x95ed8  ldarg.0
0x95ed9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x95ede  ldarg.0
0x95edf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.BindingFormattingDialog::explanationLabel
0x95ee4  ldc.i4.3
0x95ee5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x95eea  ldarg.0
0x95eeb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.BindingFormattingDialog::explanationLabel
0x95ef0  ldstr    aExplanationlab// "explanationLabel"
0x95ef5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x95efa  ldloc.0
0x95efb  ldarg.0
0x95efc  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x95f01  ldstr    aMaintablelayou// "mainTableLayoutPanel"
0x95f06  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x95f0b  ldarg.0
0x95f0c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x95f11  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0x95f16  ldc.i4.2
0x95f17  ldc.r4   100.0
0x95f1c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0x95f21  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0x95f26  pop
0x95f27  ldarg.0
0x95f28  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x95f2d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0x95f32  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor()
0x95f37  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0x95f3c  pop
0x95f3d  ldarg.0
0x95f3e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x95f43  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0x95f48  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor()
0x95f4d  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0x95f52  pop
0x95f53  ldarg.0
0x95f54  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x95f59  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x95f5e  ldarg.0
0x95f5f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::okCancelTableLayoutPanel
0x95f64  ldc.i4.2
0x95f65  ldc.i4.4
0x95f66  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x95f6b  ldarg.0
0x95f6c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x95f71  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x95f76  ldarg.0
0x95f77  ldfld    class System.Windows.Forms.Design.FormatControl System.Windows.Forms.Design.BindingFormattingDialog::formatControl1
0x95f7c  ldc.i4.1
0x95f7d  ldc.i4.3
0x95f7e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x95f83  ldarg.0
0x95f84  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x95f89  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x95f8e  ldarg.0
0x95f8f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox System.Windows.Forms.Design.BindingFormattingDialog::bindingUpdateDropDown
0x95f94  ldc.i4.2
0x95f95  ldc.i4.2
0x95f96  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x95f9b  ldarg.0
0x95f9c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x95fa1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x95fa6  ldarg.0
0x95fa7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Windows.Forms.Design.BindingFormattingDialog::propertiesTreeView
0x95fac  ldc.i4.0
0x95fad  ldc.i4.2
0x95fae  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x95fb3  ldarg.0
0x95fb4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x95fb9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x95fbe  ldarg.0
0x95fbf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.BindingFormattingDialog::updateModeLabel
0x95fc4  ldc.i4.2
0x95fc5  ldc.i4.1
0x95fc6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x95fcb  ldarg.0
0x95fcc  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x95fd1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x95fd6  ldarg.0
0x95fd7  ldfld    class System.Windows.Forms.Design.BindingFormattingWindowsFormsEditorService System.Windows.Forms.Design.BindingFormattingDialog::dataSourcePicker
0x95fdc  ldc.i4.1
0x95fdd  ldc.i4.2
0x95fde  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x95fe3  ldarg.0
0x95fe4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x95fe9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x95fee  ldarg.0
0x95fef  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.BindingFormattingDialog::explanationLabel
0x95ff4  ldc.i4.0
0x95ff5  ldc.i4.0
0x95ff6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x95ffb  ldarg.0
0x95ffc  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x96001  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x96006  ldarg.0
0x96007  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.BindingFormattingDialog::bindingLabel
0x9600c  ldc.i4.1
0x9600d  ldc.i4.1
0x9600e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x96013  ldarg.0
0x96014  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x96019  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x9601e  ldarg.0
0x9601f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.BindingFormattingDialog::propertyLabel
0x96024  ldc.i4.0
0x96025  ldc.i4.1
0x96026  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x9602b  ldarg.0
0x9602c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x96031  ldc.i4   0x21E
0x96036  ldc.i4   0x11B
0x9603b  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x96040  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x96045  ldarg.0
0x96046  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x9604b  ldstr    aMaintablelayou// "mainTableLayoutPanel"
0x96050  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x96055  ldarg.0
0x96056  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x9605b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0x96060  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor()
0x96065  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0x9606a  pop
0x9606b  ldarg.0
0x9606c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x96071  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0x96076  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor()
0x9607b  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0x96080  pop
0x96081  ldarg.0
0x96082  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x96087  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0x9608c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor()
0x96091  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0x96096  pop
0x96097  ldarg.0
0x96098  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x9609d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0x960a2  ldc.i4.2
0x960a3  ldc.r4   100.0
0x960a8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0x960ad  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0x960b2  pop
0x960b3  ldarg.0
0x960b4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x960b9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0x960be  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor()
0x960c3  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0x960c8  pop
0x960c9  ldloc.0
0x960ca  ldarg.0
0x960cb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Windows.Forms.Design.BindingFormattingDialog::propertiesTreeView
0x960d0  ldstr    aPropertiestree// "propertiesTreeView"
0x960d5  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x960da  ldarg.0
0x960db  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Windows.Forms.Design.BindingFormattingDialog::propertiesTreeView
0x960e0  ldstr    aPropertiestree// "propertiesTreeView"
0x960e5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x960ea  ldarg.0
0x960eb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Windows.Forms.Design.BindingFormattingDialog::propertiesTreeView
0x960f0  ldc.i4.0
0x960f1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_HideSelection(bool)
0x960f6  ldarg.0
0x960f7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Windows.Forms.Design.BindingFormattingDialog::propertiesTreeView
0x960fc  newobj   instance void TreeNodeComparer::.ctor()
0x96101  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_TreeViewNodeSorter(class [mscorlib]System.Collections.IComparer)
0x96106  ldarg.0
0x96107  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.BindingFormattingDialog::mainTableLayoutPanel
0x9610c  ldarg.0
0x9610d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Windows.Forms.Design.BindingFormattingDialog::propertiesTreeView
0x96112  ldc.i4.2
0x96113  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetRowSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x96118  ldarg.0
0x96119  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Windows.Forms.Design.BindingFormattingDialog::propertiesTreeView
0x9611e  ldarg.0
0x9611f  ldftn    instance void System.Windows.Forms.Design.BindingFormattingDialog::propertiesTreeView_BeforeSelect(object sender, class [System.Windows.Forms]System.Windows.Forms.TreeViewCancelEventArgs e)
0x96125  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TreeViewCancelEventHandler::.ctor(object, native int)
0x9612a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::add_BeforeSelect(class [System.Windows.Forms]System.Windows.Forms.TreeViewCancelEventHandler)
0x9612f  ldarg.0
0x96130  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Windows.Forms.Design.BindingFormattingDialog::propertiesTreeView
0x96135  ldarg.0
0x96136  ldftn    instance void System.Windows.Forms.Design.BindingFormattingDialog::propertiesTreeView_AfterSelect(object sender, class [System.Windows.Forms]System.Windows.Forms.TreeViewEventArgs e)
0x9613c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TreeViewEventHandler::.ctor(object, native int)
0x96141  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::add_AfterSelect(class [System.Windows.Forms]System.Windows.Forms.TreeViewEventHandler)
0x96146  ldloc.0
0x96147  ldarg.0
0x96148  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.BindingFormattingDialog::propertyLabel
0x9614d  ldstr    aPropertylabel// "propertyLabel"
0x96152  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x96157  ldarg.0
0x96158  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.BindingFormattingDialog::propertyLabel
0x9615d  ldstr    aPropertylabel// "propertyLabel"
0x96162  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x96167  ldloc.0
0x96168  ldarg.0
0x96169  ldfld    class System.Windows.Forms.Design.BindingFormattingWindowsFormsEditorService System.Windows.Forms.Design.BindingFormattingDialog::dataSourcePicker
0x9616e  ldstr    aDatasourcepick// "dataSourcePicker"
0x96173  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x96178  ldarg.0
0x96179  ldfld    class System.Windows.Forms.Design.BindingFormattingWindowsFormsEditorService System.Windows.Forms.Design.BindingFormattingDialog::dataSourcePicker
0x9617e  ldstr    aDatasourcepick// "dataSourcePicker"
0x96183  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x96188  ldarg.0
0x96189  ldfld    class System.Windows.Forms.Design.BindingFormattingWindowsFormsEditorService System.Windows.Forms.Design.BindingFormattingDialog::dataSourcePicker
0x9618e  ldarg.0
0x9618f  ldftn    instance void System.Windows.Forms.Design.BindingFormattingDialog::dataSourcePicker_PropertyValueChanged(object sender, class [mscorlib]System.EventArgs e)
0x96195  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x9619a  callvirt instance void System.Windows.Forms.Design.BindingFormattingWindowsFormsEditorService::add_PropertyValueChanged(class [mscorlib]System.EventHandler value)
0x9619f  ldloc.0
0x961a0  ldarg.0
0x961a1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.BindingFormattingDialog::bindingLabel
0x961a6  ldstr    aBindinglabel// "bindingLabel"
0x961ab  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x961b0  ldarg.0
0x961b1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.BindingFormattingDialog::bindingLabel
0x961b6  ldstr    aBindinglabel// "bindingLabel"
0x961bb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x961c0  ldloc.0
0x961c1  ldarg.0
0x961c2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.BindingFormattingDialog::updateModeLabel
0x961c7  ldstr    aUpdatemodelabe// "updateModeLabel"
0x961cc  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x961d1  ldarg.0
0x961d2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.BindingFormattingDialog::updateModeLabel
0x961d7  ldstr    aUpdatemodelabe// "updateModeLabel"
0x961dc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x961e1  ldarg.0
0x961e2  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox System.Windows.Forms.Design.BindingFormattingDialog::bindingUpdateDropDown
0x961e7  ldc.i4.1
0x961e8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListControl::set_FormattingEnabled(bool)
0x961ed  ldloc.0
0x961ee  ldarg.0
0x961ef  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox System.Windows.Forms.Design.BindingFormattingDialog::bindingUpdateDropDown
0x961f4  ldstr    aBindingupdated// "bindingUpdateDropDown"
0x961f9  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x961fe  ldarg.0
0x961ff  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox System.Windows.Forms.Design.BindingFormattingDialog::bindingUpdateDropDown
0x96204  ldc.i4.2
0x96205  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0x9620a  ldarg.0
0x9620b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox System.Windows.Forms.Design.BindingFormattingDialog::bindingUpdateDropDown
0x96210  ldstr    aBindingupdated// "bindingUpdateDropDown"
0x96215  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x9621a  ldarg.0
  ... truncated ...
```
