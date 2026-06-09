# Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::InitializeComponent

- ea: `0x59250`
- end: `0x59fbc`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::InitializeComponent`
- size: `3436`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x55fe0`

## callees

- `0x19710`
- `0x3a5e0`
- `0x54770`

## string_xrefs

- `0x59881`: `txtComputer`
- `0x59891`: `txtComputer`
- `0x59952`: `labelComputer`
- `0x59962`: `labelComputer`
- `0x599a6`: `comboKeywords`
- `0x599b6`: `comboKeywords`
- `0x59bab`: `labelTask`
- `0x59bbb`: `labelTask`
- `0x59bde`: `comboCategory`
- `0x59bee`: `comboCategory`
- `0x59bff`: `treeComboBoxChannels`
- `0x59c0f`: `treeComboBoxChannels`
- `0x59c20`: `comboSources`
- `0x59c30`: `comboSources`
- `0x59daa`: `tabPageXml`
- `0x59dba`: `tabPageXml`
- `0x59dcb`: `tableLayoutPanelXmlTab`
- `0x59e23`: `tableLayoutPanelXmlTab`
- `0x59e34`: `labelHowToEnterXPathMessage`
- `0x59e44`: `labelHowToEnterXPathMessage`
- `0x59ecc`: `richTextBoxXml`
- `0x59edc`: `richTextBoxXml`

## pseudocode

```c

```

## disassembly

```asm
0x59250  ldarg.0
0x59251  newobj   instance void [System]System.ComponentModel.Container::.ctor()
0x59256  stfld    class [System]System.ComponentModel.IContainer Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::components
0x5925b  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter
0x59260  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x59265  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x5926a  stloc.0
0x5926b  ldarg.0
0x5926c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabControl::.ctor()
0x59271  stfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tabControlQuery
0x59276  ldarg.0
0x59277  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x5927c  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tabPageSimpleFilter
0x59281  ldarg.0
0x59282  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x59287  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelFilterTab
0x5928c  ldarg.0
0x5928d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x59292  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::lblPeriod
0x59297  ldarg.0
0x59298  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x5929d  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::cboPeriod
0x592a2  ldarg.0
0x592a3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x592a8  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::labelEventLevel
0x592ad  ldarg.0
0x592ae  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x592b3  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::txtComputer
0x592b8  ldarg.0
0x592b9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x592be  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::txtUser
0x592c3  ldarg.0
0x592c4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x592c9  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::labelUser
0x592ce  ldarg.0
0x592cf  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x592d4  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::labelComputer
0x592d9  ldarg.0
0x592da  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x592df  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::lblKeywords
0x592e4  ldarg.0
0x592e5  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox::.ctor()
0x592ea  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::comboKeywords
0x592ef  ldarg.0
0x592f0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x592f5  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelEventLevel
0x592fa  ldarg.0
0x592fb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x59300  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::chkInf
0x59305  ldarg.0
0x59306  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x5930b  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::chkVerbose
0x59310  ldarg.0
0x59311  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x59316  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::chkCritical
0x5931b  ldarg.0
0x5931c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x59321  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::chkError
0x59326  ldarg.0
0x59327  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x5932c  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::chkWarning
0x59331  ldarg.0
0x59332  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x59337  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::labelEventId
0x5933c  ldarg.0
0x5933d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x59342  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::txtEvtId
0x59347  ldarg.0
0x59348  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x5934d  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::labelTask
0x59352  ldarg.0
0x59353  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox::.ctor()
0x59358  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::comboCategory
0x5935d  ldarg.0
0x5935e  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TreeComboBox::.ctor()
0x59363  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.TreeComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::treeComboBoxChannels
0x59368  ldarg.0
0x59369  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox::.ctor()
0x5936e  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::comboSources
0x59373  ldarg.0
0x59374  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x59379  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::btnClear
0x5937e  ldarg.0
0x5937f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x59384  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::radioButtonByLog
0x59389  ldarg.0
0x5938a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x5938f  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::lblLog
0x59394  ldarg.0
0x59395  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x5939a  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::radioButtonBySource
0x5939f  ldarg.0
0x593a0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x593a5  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::labelEventSource
0x593aa  ldarg.0
0x593ab  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x593b0  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::btnAdvance
0x593b5  ldarg.0
0x593b6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x593bb  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tabPageXml
0x593c0  ldarg.0
0x593c1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x593c6  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelXmlTab
0x593cb  ldarg.0
0x593cc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x593d1  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::labelHowToEnterXPathMessage
0x593d6  ldarg.0
0x593d7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x593dc  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::chkEditQuery
0x593e1  ldarg.0
0x593e2  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.RichTextBox5::.ctor()
0x593e7  stfld    class [System.Windows.Forms]System.Windows.Forms.RichTextBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::richTextBoxXml
0x593ec  ldarg.0
0x593ed  ldarg.0
0x593ee  ldfld    class [System]System.ComponentModel.IContainer Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::components
0x593f3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolTip::.ctor(class [System]System.ComponentModel.IContainer)
0x593f8  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolTip Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::toolTip
0x593fd  ldarg.0
0x593fe  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tabControlQuery
0x59403  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x59408  ldarg.0
0x59409  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tabPageSimpleFilter
0x5940e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x59413  ldarg.0
0x59414  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelFilterTab
0x59419  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x5941e  ldarg.0
0x5941f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelEventLevel
0x59424  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x59429  ldarg.0
0x5942a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tabPageXml
0x5942f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x59434  ldarg.0
0x59435  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelXmlTab
0x5943a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x5943f  ldarg.0
0x59440  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x59445  ldarg.0
0x59446  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tabControlQuery
0x5944b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x59450  ldarg.0
0x59451  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tabPageSimpleFilter
0x59456  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x5945b  ldarg.0
0x5945c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tabControlQuery
0x59461  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x59466  ldarg.0
0x59467  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tabPageXml
0x5946c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x59471  ldloc.0
0x59472  ldarg.0
0x59473  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tabControlQuery
0x59478  ldstr    aTabcontrolquer// "tabControlQuery"
0x5947d  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x59482  ldarg.0
0x59483  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tabControlQuery
0x59488  ldstr    aTabcontrolquer// "tabControlQuery"
0x5948d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x59492  ldarg.0
0x59493  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tabControlQuery
0x59498  ldc.i4.0
0x59499  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabControl::set_SelectedIndex(int32)
0x5949e  ldarg.0
0x5949f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tabControlQuery
0x594a4  ldarg.0
0x594a5  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tbQuery_Selecting(object sender, class [System.Windows.Forms]System.Windows.Forms.TabControlCancelEventArgs e)
0x594ab  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabControlCancelEventHandler::.ctor(object, native int)
0x594b0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabControl::add_Selecting(class [System.Windows.Forms]System.Windows.Forms.TabControlCancelEventHandler)
0x594b5  ldarg.0
0x594b6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tabPageSimpleFilter
0x594bb  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x594c0  ldarg.0
0x594c1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelFilterTab
0x594c6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x594cb  ldarg.0
0x594cc  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tabPageSimpleFilter
0x594d1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x594d6  ldarg.0
0x594d7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::btnAdvance
0x594dc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x594e1  ldloc.0
0x594e2  ldarg.0
0x594e3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tabPageSimpleFilter
0x594e8  ldstr    aTabpagesimplef// "tabPageSimpleFilter"
0x594ed  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x594f2  ldarg.0
0x594f3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tabPageSimpleFilter
0x594f8  ldstr    aTabpagesimplef// "tabPageSimpleFilter"
0x594fd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x59502  ldloc.0
0x59503  ldarg.0
0x59504  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelFilterTab
0x59509  ldstr    aTablelayoutpan_6// "tableLayoutPanelFilterTab"
0x5950e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x59513  ldarg.0
0x59514  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelFilterTab
0x59519  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x5951e  ldarg.0
0x5951f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::lblPeriod
0x59524  ldc.i4.0
0x59525  ldc.i4.0
0x59526  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x5952b  ldarg.0
0x5952c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelFilterTab
0x59531  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x59536  ldarg.0
0x59537  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::cboPeriod
0x5953c  ldc.i4.1
0x5953d  ldc.i4.0
0x5953e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x59543  ldarg.0
0x59544  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelFilterTab
0x59549  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x5954e  ldarg.0
0x5954f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::labelEventLevel
0x59554  ldc.i4.0
0x59555  ldc.i4.1
0x59556  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x5955b  ldarg.0
0x5955c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelFilterTab
0x59561  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x59566  ldarg.0
0x59567  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::txtComputer
0x5956c  ldc.i4.1
0x5956d  ldc.i4.s 9
0x5956f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x59574  ldarg.0
0x59575  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelFilterTab
0x5957a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x5957f  ldarg.0
0x59580  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::txtUser
0x59585  ldc.i4.1
0x59586  ldc.i4.8
0x59587  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x5958c  ldarg.0
0x5958d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelFilterTab
0x59592  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x59597  ldarg.0
0x59598  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::labelUser
0x5959d  ldc.i4.0
0x5959e  ldc.i4.8
0x5959f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x595a4  ldarg.0
0x595a5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelFilterTab
0x595aa  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x595af  ldarg.0
0x595b0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::labelComputer
0x595b5  ldc.i4.0
0x595b6  ldc.i4.s 9
0x595b8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x595bd  ldarg.0
0x595be  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelFilterTab
0x595c3  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x595c8  ldarg.0
0x595c9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::lblKeywords
0x595ce  ldc.i4.0
0x595cf  ldc.i4.7
0x595d0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x595d5  ldarg.0
0x595d6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelFilterTab
0x595db  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x595e0  ldarg.0
0x595e1  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CheckedListComboBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::comboKeywords
0x595e6  ldc.i4.1
0x595e7  ldc.i4.7
0x595e8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x595ed  ldarg.0
0x595ee  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelFilterTab
0x595f3  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x595f8  ldarg.0
0x595f9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelEventLevel
0x595fe  ldc.i4.1
0x595ff  ldc.i4.1
0x59600  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x59605  ldarg.0
0x59606  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelFilterTab
0x5960b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x59610  ldarg.0
0x59611  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::labelEventId
0x59616  ldc.i4.0
0x59617  ldc.i4.4
0x59618  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x5961d  ldarg.0
0x5961e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelFilterTab
0x59623  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x59628  ldarg.0
0x59629  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::txtEvtId
0x5962e  ldc.i4.1
0x5962f  ldc.i4.5
0x59630  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x59635  ldarg.0
0x59636  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelFilterTab
0x5963b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x59640  ldarg.0
0x59641  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::labelTask
0x59646  ldc.i4.0
0x59647  ldc.i4.6
0x59648  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x5964d  ldarg.0
0x5964e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::tableLayoutPanelFilterTab
  ... truncated ...
```
