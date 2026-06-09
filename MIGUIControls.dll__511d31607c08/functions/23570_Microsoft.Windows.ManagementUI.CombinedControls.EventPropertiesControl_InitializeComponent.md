# Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::InitializeComponent

- ea: `0x23570`
- end: `0x2436d`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::InitializeComponent`
- size: `3581`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x227d0`

## callees

- `0x12ed0`
- `0x1fa20`
- `0x23570`
- `0x25000`
- `0x3a5e0`

## string_xrefs

- `0x23772`: `xmlViewContextMenuStrip1`
- `0x237c4`: `copyAsTextToolStripMenuItem`
- `0x237d4`: `copyAsTextToolStripMenuItem`
- `0x23cae`: `PathLabel`
- `0x23cbe`: `PathLabel`
- `0x23e6a`: `pathTextBox`
- `0x23e7a`: `pathTextBox`
- `0x23e97`: `computerLabel`
- `0x23ea7`: `computerLabel`
- `0x23ed9`: `TaskLabel`
- `0x23ee9`: `TaskLabel`
- `0x23f37`: `computerTextBox`
- `0x23f47`: `computerTextBox`
- `0x23fc9`: `TaskTextBox`
- `0x23fd9`: `TaskTextBox`
- `0x2414e`: `tableXmlBottomPanel`
- `0x24176`: `tableXmlBottomPanel`
- `0x24187`: `xmlViewCtl`
- `0x24197`: `xmlViewCtl`
- `0x241d6`: `tableXmlTopPanel`
- `0x24216`: `tableXmlTopPanel`
- `0x2426b`: `xmlViewRadioButton`
- `0x2427b`: `xmlViewRadioButton`

## pseudocode

```c

```

## disassembly

```asm
0x23570  ldarg.0
0x23571  newobj   instance void [System]System.ComponentModel.Container::.ctor()
0x23576  stfld    class [System]System.ComponentModel.IContainer Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::components
0x2357b  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl
0x23580  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23585  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x2358a  stloc.0
0x2358b  ldarg.0
0x2358c  ldarg.0
0x2358d  ldfld    class [System]System.ComponentModel.IContainer Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::components
0x23592  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ContextMenuStrip::.ctor(class [System]System.ComponentModel.IContainer)
0x23597  stfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenuStrip Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::xmlViewContextMenuStrip1
0x2359c  ldarg.0
0x2359d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem::.ctor()
0x235a2  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::copyAsTextToolStripMenuItem
0x235a7  ldarg.0
0x235a8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripSeparator::.ctor()
0x235ad  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSeparator Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::toolStripSeparator1
0x235b2  ldarg.0
0x235b3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem::.ctor()
0x235b8  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::selectAllToolStripMenuItem
0x235bd  ldarg.0
0x235be  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx::.ctor()
0x235c3  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabProperties
0x235c8  ldarg.0
0x235c9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x235ce  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabGeneral
0x235d3  ldarg.0
0x235d4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x235d9  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tableLayoutGeneral
0x235de  ldarg.0
0x235df  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.RichTextBox5::.ctor()
0x235e4  stfld    class [System.Windows.Forms]System.Windows.Forms.RichTextBox Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::messageRichTextBox
0x235e9  ldarg.0
0x235ea  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x235ef  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::opCodeLabel
0x235f4  ldarg.0
0x235f5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x235fa  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::userLabel
0x235ff  ldarg.0
0x23600  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x23605  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::eventLevelLabel
0x2360a  ldarg.0
0x2360b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x23610  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::eventIDLabel
0x23615  ldarg.0
0x23616  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x2361b  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::sourceLabel
0x23620  ldarg.0
0x23621  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x23626  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::PathLabel
0x2362b  ldarg.0
0x2362c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x23631  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::opCodeTextBox
0x23636  ldarg.0
0x23637  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x2363c  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::userTextBox
0x23641  ldarg.0
0x23642  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x23647  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::eventLevelTextBox
0x2364c  ldarg.0
0x2364d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x23652  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::eventIDTextBox
0x23657  ldarg.0
0x23658  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x2365d  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::sourceTextBox
0x23662  ldarg.0
0x23663  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x23668  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::pathTextBox
0x2366d  ldarg.0
0x2366e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x23673  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::computerLabel
0x23678  ldarg.0
0x23679  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x2367e  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::keywordsLabel
0x23683  ldarg.0
0x23684  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x23689  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::TaskLabel
0x2368e  ldarg.0
0x2368f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x23694  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::dateLabel
0x23699  ldarg.0
0x2369a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x2369f  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::computerTextBox
0x236a4  ldarg.0
0x236a5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x236aa  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::keyWordTextBox
0x236af  ldarg.0
0x236b0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x236b5  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::TaskTextBox
0x236ba  ldarg.0
0x236bb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x236c0  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::dateTextBox
0x236c5  ldarg.0
0x236c6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TabPage::.ctor()
0x236cb  stfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabDetails
0x236d0  ldarg.0
0x236d1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x236d6  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tableXmlBottomPanel
0x236db  ldarg.0
0x236dc  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.WebBrowserEx::.ctor()
0x236e1  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.WebBrowserEx Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::xmlViewCtl
0x236e6  ldarg.0
0x236e7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x236ec  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tableXmlTopPanel
0x236f1  ldarg.0
0x236f2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x236f7  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::friendlyViewRadioButton
0x236fc  ldarg.0
0x236fd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x23702  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::xmlViewRadioButton
0x23707  ldarg.0
0x23708  ldarg.0
0x23709  ldfld    class [System]System.ComponentModel.IContainer Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::components
0x2370e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolTip::.ctor(class [System]System.ComponentModel.IContainer)
0x23713  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolTip Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::toolTip1
0x23718  ldarg.0
0x23719  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenuStrip Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::xmlViewContextMenuStrip1
0x2371e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x23723  ldarg.0
0x23724  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabProperties
0x23729  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x2372e  ldarg.0
0x2372f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabGeneral
0x23734  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x23739  ldarg.0
0x2373a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tableLayoutGeneral
0x2373f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x23744  ldarg.0
0x23745  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabDetails
0x2374a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x2374f  ldarg.0
0x23750  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tableXmlBottomPanel
0x23755  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x2375a  ldarg.0
0x2375b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tableXmlTopPanel
0x23760  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x23765  ldarg.0
0x23766  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x2376b  ldloc.0
0x2376c  ldarg.0
0x2376d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenuStrip Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::xmlViewContextMenuStrip1
0x23772  ldstr    aXmlviewcontext// "xmlViewContextMenuStrip1"
0x23777  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x2377c  ldarg.0
0x2377d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenuStrip Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::xmlViewContextMenuStrip1
0x23782  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0x23787  ldc.i4.3
0x23788  newarr   [System.Windows.Forms]System.Windows.Forms.ToolStripItem
0x2378d  dup
0x2378e  ldc.i4.0
0x2378f  ldarg.0
0x23790  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::copyAsTextToolStripMenuItem
0x23795  stelem.ref
0x23796  dup
0x23797  ldc.i4.1
0x23798  ldarg.0
0x23799  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSeparator Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::toolStripSeparator1
0x2379e  stelem.ref
0x2379f  dup
0x237a0  ldc.i4.2
0x237a1  ldarg.0
0x237a2  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::selectAllToolStripMenuItem
0x237a7  stelem.ref
0x237a8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::AddRange(class [System.Windows.Forms]System.Windows.Forms.ToolStripItem[])
0x237ad  ldarg.0
0x237ae  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenuStrip Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::xmlViewContextMenuStrip1
0x237b3  ldstr    aContextmenustr// "contextMenuStrip1"
0x237b8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x237bd  ldloc.0
0x237be  ldarg.0
0x237bf  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::copyAsTextToolStripMenuItem
0x237c4  ldstr    aCopyastexttool// "copyAsTextToolStripMenuItem"
0x237c9  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x237ce  ldarg.0
0x237cf  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::copyAsTextToolStripMenuItem
0x237d4  ldstr    aCopyastexttool// "copyAsTextToolStripMenuItem"
0x237d9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Name(string)
0x237de  ldarg.0
0x237df  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::copyAsTextToolStripMenuItem
0x237e4  ldarg.0
0x237e5  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::copyAsTextToolStripMenuItem_Click(object sender, class [mscorlib]System.EventArgs e)
0x237eb  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x237f0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::add_Click(class [mscorlib]System.EventHandler)
0x237f5  ldloc.0
0x237f6  ldarg.0
0x237f7  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSeparator Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::toolStripSeparator1
0x237fc  ldstr    aToolstripsepar// "toolStripSeparator1"
0x23801  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x23806  ldarg.0
0x23807  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSeparator Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::toolStripSeparator1
0x2380c  ldstr    aToolstripsepar// "toolStripSeparator1"
0x23811  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Name(string)
0x23816  ldloc.0
0x23817  ldarg.0
0x23818  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::selectAllToolStripMenuItem
0x2381d  ldstr    aSelectalltools// "selectAllToolStripMenuItem"
0x23822  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x23827  ldarg.0
0x23828  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::selectAllToolStripMenuItem
0x2382d  ldstr    aSelectalltools// "selectAllToolStripMenuItem"
0x23832  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Name(string)
0x23837  ldarg.0
0x23838  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::selectAllToolStripMenuItem
0x2383d  ldarg.0
0x2383e  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::selectAllToolStripMenuItem_Click(object sender, class [mscorlib]System.EventArgs e)
0x23844  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x23849  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::add_Click(class [mscorlib]System.EventHandler)
0x2384e  ldarg.0
0x2384f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabProperties
0x23854  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x23859  ldarg.0
0x2385a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabGeneral
0x2385f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x23864  ldarg.0
0x23865  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabProperties
0x2386a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x2386f  ldarg.0
0x23870  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabDetails
0x23875  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x2387a  ldloc.0
0x2387b  ldarg.0
0x2387c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabProperties
0x23881  ldstr    aTabproperties// "tabProperties"
0x23886  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x2388b  ldarg.0
0x2388c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabProperties
0x23891  ldstr    aTabproperties// "tabProperties"
0x23896  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2389b  ldarg.0
0x2389c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabProperties
0x238a1  ldc.i4.0
0x238a2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabControl::set_SelectedIndex(int32)
0x238a7  ldarg.0
0x238a8  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabProperties
0x238ad  ldarg.0
0x238ae  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabProperties_Layout(object sender, class [System.Windows.Forms]System.Windows.Forms.LayoutEventArgs e)
0x238b4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LayoutEventHandler::.ctor(object, native int)
0x238b9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Layout(class [System.Windows.Forms]System.Windows.Forms.LayoutEventHandler)
0x238be  ldarg.0
0x238bf  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabProperties
0x238c4  ldarg.0
0x238c5  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabProperties_HelpRequested(object sender, class [System.Windows.Forms]System.Windows.Forms.HelpEventArgs hlpevent)
0x238cb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.HelpEventHandler::.ctor(object, native int)
0x238d0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_HelpRequested(class [System.Windows.Forms]System.Windows.Forms.HelpEventHandler)
0x238d5  ldarg.0
0x238d6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabProperties
0x238db  ldarg.0
0x238dc  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabProperties_SelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x238e2  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x238e7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TabControl::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x238ec  ldloc.0
0x238ed  ldarg.0
0x238ee  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabGeneral
0x238f3  ldstr    aTabgeneral// "tabGeneral"
0x238f8  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x238fd  ldarg.0
0x238fe  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabGeneral
0x23903  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x23908  ldarg.0
0x23909  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tableLayoutGeneral
0x2390e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x23913  ldarg.0
0x23914  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabGeneral
0x23919  ldstr    aTabgeneral// "tabGeneral"
0x2391e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x23923  ldarg.0
0x23924  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabGeneral
0x23929  ldarg.0
0x2392a  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabGeneral_Layout(object sender, class [System.Windows.Forms]System.Windows.Forms.LayoutEventArgs e)
0x23930  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LayoutEventHandler::.ctor(object, native int)
0x23935  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Layout(class [System.Windows.Forms]System.Windows.Forms.LayoutEventHandler)
0x2393a  ldloc.0
0x2393b  ldarg.0
0x2393c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tableLayoutGeneral
0x23941  ldstr    aTablelayoutgen// "tableLayoutGeneral"
0x23946  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x2394b  ldarg.0
0x2394c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tableLayoutGeneral
0x23951  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x23956  ldarg.0
0x23957  ldfld    class [System.Windows.Forms]System.Windows.Forms.RichTextBox Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::messageRichTextBox
0x2395c  ldc.i4.0
0x2395d  ldc.i4.0
0x2395e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x23963  ldarg.0
0x23964  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tableLayoutGeneral
0x23969  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x2396e  ldarg.0
0x2396f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::opCodeLabel
0x23974  ldc.i4.0
0x23975  ldc.i4.6
0x23976  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x2397b  ldarg.0
0x2397c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tableLayoutGeneral
0x23981  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x23986  ldarg.0
0x23987  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::userLabel
0x2398c  ldc.i4.0
0x2398d  ldc.i4.5
  ... truncated ...
```
