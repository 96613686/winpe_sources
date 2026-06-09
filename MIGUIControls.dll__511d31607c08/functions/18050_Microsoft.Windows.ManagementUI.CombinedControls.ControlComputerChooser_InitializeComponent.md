# Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::InitializeComponent

- ea: `0x18050`
- end: `0x1842e`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::InitializeComponent`
- size: `990`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x17b30`

## string_xrefs

- `0x18313`: `textBoxRemoteComputerName`
- `0x18323`: `textBoxRemoteComputerName`
- `0x183f3`: `ControlComputerChooser`

## pseudocode

```c

```

## disassembly

```asm
0x18050  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser
0x18055  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1805a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x1805f  ldarg.0
0x18060  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x18065  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::labelDescription
0x1806a  ldarg.0
0x1806b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x18070  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::radioButtonRemote
0x18075  ldarg.0
0x18076  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x1807b  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::radioButtonLocal
0x18080  ldarg.0
0x18081  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x18086  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::buttonBrowse
0x1808b  ldarg.0
0x1808c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x18091  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::tableLayoutPanel
0x18096  ldarg.0
0x18097  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x1809c  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::buttonSetUser
0x180a1  ldarg.0
0x180a2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x180a7  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::textBoxRemoteComputerName
0x180ac  ldarg.0
0x180ad  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x180b2  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::checkBoxAnotherUser
0x180b7  ldarg.0
0x180b8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::tableLayoutPanel
0x180bd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x180c2  ldarg.0
0x180c3  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x180c8  ldarg.0
0x180c9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::tableLayoutPanel
0x180ce  ldarg.0
0x180cf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::labelDescription
0x180d4  ldc.i4.3
0x180d5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x180da  dup
0x180db  ldarg.0
0x180dc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::labelDescription
0x180e1  ldstr    aLabeldescripti// "labelDescription"
0x180e6  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x180eb  ldarg.0
0x180ec  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::labelDescription
0x180f1  ldstr    aLabeldescripti// "labelDescription"
0x180f6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x180fb  dup
0x180fc  ldarg.0
0x180fd  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::radioButtonRemote
0x18102  ldstr    aRadiobuttonrem// "radioButtonRemote"
0x18107  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1810c  ldarg.0
0x1810d  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::radioButtonRemote
0x18112  ldstr    aRadiobuttonrem// "radioButtonRemote"
0x18117  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1811c  ldarg.0
0x1811d  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::radioButtonRemote
0x18122  ldc.i4.1
0x18123  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_TabStop(bool)
0x18128  ldarg.0
0x18129  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::radioButtonRemote
0x1812e  ldarg.0
0x1812f  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::radioButtonRemote_Click(object sender, class [mscorlib]System.EventArgs e)
0x18135  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1813a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x1813f  ldarg.0
0x18140  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::radioButtonLocal
0x18145  ldc.i4.1
0x18146  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_Checked(bool)
0x1814b  ldarg.0
0x1814c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::tableLayoutPanel
0x18151  ldarg.0
0x18152  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::radioButtonLocal
0x18157  ldc.i4.3
0x18158  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x1815d  dup
0x1815e  ldarg.0
0x1815f  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::radioButtonLocal
0x18164  ldstr    aRadiobuttonloc// "radioButtonLocal"
0x18169  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1816e  ldarg.0
0x1816f  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::radioButtonLocal
0x18174  ldstr    aRadiobuttonloc// "radioButtonLocal"
0x18179  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1817e  ldarg.0
0x1817f  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::radioButtonLocal
0x18184  ldc.i4.1
0x18185  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_TabStop(bool)
0x1818a  ldarg.0
0x1818b  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::radioButtonLocal
0x18190  ldarg.0
0x18191  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::radioButtonLocal_Click(object sender, class [mscorlib]System.EventArgs e)
0x18197  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1819c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x181a1  dup
0x181a2  ldarg.0
0x181a3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::buttonBrowse
0x181a8  ldstr    aButtonbrowse// "buttonBrowse"
0x181ad  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x181b2  ldarg.0
0x181b3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::buttonBrowse
0x181b8  ldstr    aButtonbrowse// "buttonBrowse"
0x181bd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x181c2  ldarg.0
0x181c3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::buttonBrowse
0x181c8  ldc.i4.s 0x20
0x181ca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0x181cf  ldarg.0
0x181d0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::buttonBrowse
0x181d5  ldarg.0
0x181d6  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::buttonBrowse_Click(object sender, class [mscorlib]System.EventArgs e)
0x181dc  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x181e1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x181e6  dup
0x181e7  ldarg.0
0x181e8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::tableLayoutPanel
0x181ed  ldstr    aTablelayoutpan_0// "tableLayoutPanel"
0x181f2  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x181f7  ldarg.0
0x181f8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::tableLayoutPanel
0x181fd  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x18202  ldarg.0
0x18203  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::buttonSetUser
0x18208  ldc.i4.2
0x18209  ldc.i4.3
0x1820a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x1820f  ldarg.0
0x18210  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::tableLayoutPanel
0x18215  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x1821a  ldarg.0
0x1821b  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::radioButtonLocal
0x18220  ldc.i4.0
0x18221  ldc.i4.1
0x18222  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x18227  ldarg.0
0x18228  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::tableLayoutPanel
0x1822d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x18232  ldarg.0
0x18233  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::labelDescription
0x18238  ldc.i4.0
0x18239  ldc.i4.0
0x1823a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x1823f  ldarg.0
0x18240  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::tableLayoutPanel
0x18245  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x1824a  ldarg.0
0x1824b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::buttonBrowse
0x18250  ldc.i4.2
0x18251  ldc.i4.2
0x18252  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x18257  ldarg.0
0x18258  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::tableLayoutPanel
0x1825d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x18262  ldarg.0
0x18263  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::textBoxRemoteComputerName
0x18268  ldc.i4.1
0x18269  ldc.i4.2
0x1826a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x1826f  ldarg.0
0x18270  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::tableLayoutPanel
0x18275  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x1827a  ldarg.0
0x1827b  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::radioButtonRemote
0x18280  ldc.i4.0
0x18281  ldc.i4.2
0x18282  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x18287  ldarg.0
0x18288  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::tableLayoutPanel
0x1828d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x18292  ldarg.0
0x18293  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::checkBoxAnotherUser
0x18298  ldc.i4.0
0x18299  ldc.i4.3
0x1829a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x1829f  ldarg.0
0x182a0  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::tableLayoutPanel
0x182a5  ldc.i4.0
0x182a6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::set_GrowStyle(valuetype [System.Windows.Forms]System.Windows.Forms.TableLayoutPanelGrowStyle)
0x182ab  ldarg.0
0x182ac  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::tableLayoutPanel
0x182b1  ldstr    aTablelayoutpan_0// "tableLayoutPanel"
0x182b6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x182bb  dup
0x182bc  ldarg.0
0x182bd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::buttonSetUser
0x182c2  ldstr    aButtonsetuser// "buttonSetUser"
0x182c7  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x182cc  ldarg.0
0x182cd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::buttonSetUser
0x182d2  ldstr    aButtonsetuser// "buttonSetUser"
0x182d7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x182dc  ldarg.0
0x182dd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::buttonSetUser
0x182e2  ldc.i4.s 0x20
0x182e4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0x182e9  ldarg.0
0x182ea  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::buttonSetUser
0x182ef  ldarg.0
0x182f0  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::buttonSetUser_Click(object sender, class [mscorlib]System.EventArgs e)
0x182f6  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x182fb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x18300  ldarg.0
0x18301  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::textBoxRemoteComputerName
0x18306  ldc.i4.1
0x18307  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBox::set_CharacterCasing(valuetype [System.Windows.Forms]System.Windows.Forms.CharacterCasing)
0x1830c  dup
0x1830d  ldarg.0
0x1830e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::textBoxRemoteComputerName
0x18313  ldstr    aTextboxremotec// "textBoxRemoteComputerName"
0x18318  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1831d  ldarg.0
0x1831e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::textBoxRemoteComputerName
0x18323  ldstr    aTextboxremotec// "textBoxRemoteComputerName"
0x18328  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1832d  ldarg.0
0x1832e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::textBoxRemoteComputerName
0x18333  ldarg.0
0x18334  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::radioButtonRemote
0x18339  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x1833e  ldstr    asc_AA3F0// "&"
0x18343  ldstr    asc_AA3F4// ""
0x18348  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1834d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x18352  ldarg.0
0x18353  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::textBoxRemoteComputerName
0x18358  ldarg.0
0x18359  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::textBoxRemoteComputerName_Leave(object sender, class [mscorlib]System.EventArgs e)
0x1835f  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x18364  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Leave(class [mscorlib]System.EventHandler)
0x18369  ldarg.0
0x1836a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::textBoxRemoteComputerName
0x1836f  ldarg.0
0x18370  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::textBoxRemoteComputerName_TextChanged(object sender, class [mscorlib]System.EventArgs e)
0x18376  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1837b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x18380  ldarg.0
0x18381  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::tableLayoutPanel
0x18386  ldarg.0
0x18387  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::checkBoxAnotherUser
0x1838c  ldc.i4.2
0x1838d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x18392  dup
0x18393  ldarg.0
0x18394  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::checkBoxAnotherUser
0x18399  ldstr    aCheckboxanothe// "checkBoxAnotherUser"
0x1839e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x183a3  ldarg.0
0x183a4  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::checkBoxAnotherUser
0x183a9  ldstr    aCheckboxanothe// "checkBoxAnotherUser"
0x183ae  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x183b3  ldarg.0
0x183b4  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::checkBoxAnotherUser
0x183b9  ldc.i4.1
0x183ba  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x183bf  ldarg.0
0x183c0  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::checkBoxAnotherUser
0x183c5  ldarg.0
0x183c6  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::checkBoxAnotherUser_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x183cc  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x183d1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x183d6  ldarg.0
0x183d7  ldstr    aThis// "$this"
0x183dc  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x183e1  ldarg.0
0x183e2  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x183e7  ldarg.0
0x183e8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::tableLayoutPanel
0x183ed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x183f2  ldarg.0
0x183f3  ldstr    aControlcompute_0// "ControlComputerChooser"
0x183f8  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x183fd  ldarg.0
0x183fe  ldarg.0
0x183ff  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::ControlComputerChooser_Load(object sender, class [mscorlib]System.EventArgs e)
0x18405  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1840a  call     instance void [System.Windows.Forms]System.Windows.Forms.UserControl::add_Load(class [mscorlib]System.EventHandler)
0x1840f  ldarg.0
0x18410  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::tableLayoutPanel
0x18415  ldc.i4.0
0x18416  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x1841b  ldarg.0
0x1841c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::tableLayoutPanel
0x18421  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x18426  ldarg.0
0x18427  ldc.i4.0
0x18428  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x1842d  ret
```
