# System.Deployment.Application.MaintenancePiece::InitializeComponent

- ea: `0x180c0`
- end: `0x18d05`
- name: `System.Deployment.Application.MaintenancePiece::InitializeComponent`
- size: `3141`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000`

## callees

- `0x9d0`
- `0x180c0`
- `0x23020`

## string_xrefs

- `0x182c9`: `pictureRemove`
- `0x182f1`: `pictureRemove`
- `0x1836a`: `radioRemove`
- `0x18392`: `radioRemove`
- `0x18ac7`: `ClickOnceRemoveIcon`

## pseudocode

```c

```

## disassembly

```asm
0x180c0  ldtoken  System.Deployment.Application.MaintenancePiece
0x180c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x180ca  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x180cf  stloc.0
0x180d0  ldarg.0
0x180d1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x180d6  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.MaintenancePiece::lblHeader
0x180db  ldarg.0
0x180dc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x180e1  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.MaintenancePiece::lblSubHeader
0x180e6  ldarg.0
0x180e7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0x180ec  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureRestore
0x180f1  ldarg.0
0x180f2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0x180f7  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureRemove
0x180fc  ldarg.0
0x180fd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x18102  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Deployment.Application.MaintenancePiece::radioRestore
0x18107  ldarg.0
0x18108  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x1810d  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Deployment.Application.MaintenancePiece::radioRemove
0x18112  ldarg.0
0x18113  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x18118  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.MaintenancePiece::groupRule
0x1811d  ldarg.0
0x1811e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x18123  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.MaintenancePiece::groupDivider
0x18128  ldarg.0
0x18129  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x1812e  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.MaintenancePiece::btnOk
0x18133  ldarg.0
0x18134  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x18139  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.MaintenancePiece::btnCancel
0x1813e  ldarg.0
0x1813f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x18144  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.MaintenancePiece::btnHelp
0x18149  ldarg.0
0x1814a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x1814f  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.MaintenancePiece::topTableLayoutPanel
0x18154  ldarg.0
0x18155  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0x1815a  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureDesktop
0x1815f  ldarg.0
0x18160  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x18165  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.MaintenancePiece::okCancelHelpTableLayoutPanel
0x1816a  ldarg.0
0x1816b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x18170  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.MaintenancePiece::contentTableLayoutPanel
0x18175  ldarg.0
0x18176  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x1817b  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.MaintenancePiece::overarchingTableLayoutPanel
0x18180  ldarg.0
0x18181  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureRestore
0x18186  callvirt instance void [System]System.ComponentModel.ISupportInitialize::BeginInit()
0x1818b  ldarg.0
0x1818c  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureRemove
0x18191  callvirt instance void [System]System.ComponentModel.ISupportInitialize::BeginInit()
0x18196  ldarg.0
0x18197  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.MaintenancePiece::topTableLayoutPanel
0x1819c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x181a1  ldarg.0
0x181a2  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureDesktop
0x181a7  callvirt instance void [System]System.ComponentModel.ISupportInitialize::BeginInit()
0x181ac  ldarg.0
0x181ad  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.MaintenancePiece::okCancelHelpTableLayoutPanel
0x181b2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x181b7  ldarg.0
0x181b8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.MaintenancePiece::contentTableLayoutPanel
0x181bd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x181c2  ldarg.0
0x181c3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.MaintenancePiece::overarchingTableLayoutPanel
0x181c8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x181cd  ldarg.0
0x181ce  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x181d3  ldarg.0
0x181d4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.MaintenancePiece::lblHeader
0x181d9  ldc.i4.1
0x181da  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_AutoEllipsis(bool)
0x181df  ldloc.0
0x181e0  ldarg.0
0x181e1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.MaintenancePiece::lblHeader
0x181e6  ldstr    aLblheader// "lblHeader"
0x181eb  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x181f0  ldarg.0
0x181f1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.MaintenancePiece::lblHeader
0x181f6  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits10
0x181fb  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits11
0x18200  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x18205  ldc.i4.0
0x18206  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x1820b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x18210  ldarg.0
0x18211  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.MaintenancePiece::lblHeader
0x18216  ldstr    aLblheader// "lblHeader"
0x1821b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x18220  ldarg.0
0x18221  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.MaintenancePiece::lblHeader
0x18226  ldc.i4.0
0x18227  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_UseMnemonic(bool)
0x1822c  ldloc.0
0x1822d  ldarg.0
0x1822e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.MaintenancePiece::lblSubHeader
0x18233  ldstr    aLblsubheader// "lblSubHeader"
0x18238  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1823d  ldarg.0
0x1823e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.MaintenancePiece::lblSubHeader
0x18243  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits29
0x18248  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x1824d  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x18252  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits8
0x18257  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x1825c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x18261  ldarg.0
0x18262  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.MaintenancePiece::lblSubHeader
0x18267  ldstr    aLblsubheader// "lblSubHeader"
0x1826c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x18271  ldloc.0
0x18272  ldarg.0
0x18273  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureRestore
0x18278  ldstr    aPicturerestore// "pictureRestore"
0x1827d  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x18282  ldarg.0
0x18283  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureRestore
0x18288  ldc.i4.0
0x18289  ldc.i4.0
0x1828a  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x1828f  ldc.i4.0
0x18290  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x18295  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x1829a  ldarg.0
0x1829b  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureRestore
0x182a0  ldstr    aPicturerestore// "pictureRestore"
0x182a5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x182aa  ldarg.0
0x182ab  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureRestore
0x182b0  ldc.i4.0
0x182b1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_TabStop(bool)
0x182b6  ldarg.0
0x182b7  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureRestore
0x182bc  ldc.i4.2
0x182bd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_SizeMode(valuetype [System.Windows.Forms]System.Windows.Forms.PictureBoxSizeMode)
0x182c2  ldloc.0
0x182c3  ldarg.0
0x182c4  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureRemove
0x182c9  ldstr    aPictureremove// "pictureRemove"
0x182ce  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x182d3  ldarg.0
0x182d4  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureRemove
0x182d9  ldc.i4.0
0x182da  ldc.i4.0
0x182db  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x182e0  ldc.i4.0
0x182e1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x182e6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x182eb  ldarg.0
0x182ec  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureRemove
0x182f1  ldstr    aPictureremove// "pictureRemove"
0x182f6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x182fb  ldarg.0
0x182fc  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureRemove
0x18301  ldc.i4.0
0x18302  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_TabStop(bool)
0x18307  ldarg.0
0x18308  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.MaintenancePiece::pictureRemove
0x1830d  ldc.i4.2
0x1830e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_SizeMode(valuetype [System.Windows.Forms]System.Windows.Forms.PictureBoxSizeMode)
0x18313  ldloc.0
0x18314  ldarg.0
0x18315  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Deployment.Application.MaintenancePiece::radioRestore
0x1831a  ldstr    aRadiorestore// "radioRestore"
0x1831f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x18324  ldarg.0
0x18325  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Deployment.Application.MaintenancePiece::radioRestore
0x1832a  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x1832f  ldc.i4.0
0x18330  ldc.i4.0
0x18331  ldc.i4.0
0x18332  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x18337  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x1833c  ldarg.0
0x1833d  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Deployment.Application.MaintenancePiece::radioRestore
0x18342  ldstr    aRadiorestore// "radioRestore"
0x18347  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1834c  ldarg.0
0x1834d  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Deployment.Application.MaintenancePiece::radioRestore
0x18352  ldarg.0
0x18353  ldftn    instance void System.Deployment.Application.MaintenancePiece::radioRestore_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x18359  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1835e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x18363  ldloc.0
0x18364  ldarg.0
0x18365  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Deployment.Application.MaintenancePiece::radioRemove
0x1836a  ldstr    aRadioremove// "radioRemove"
0x1836f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x18374  ldarg.0
0x18375  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Deployment.Application.MaintenancePiece::radioRemove
0x1837a  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x1837f  ldc.i4.0
0x18380  ldc.i4.0
0x18381  ldc.i4.0
0x18382  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x18387  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x1838c  ldarg.0
0x1838d  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Deployment.Application.MaintenancePiece::radioRemove
0x18392  ldstr    aRadioremove// "radioRemove"
0x18397  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1839c  ldarg.0
0x1839d  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Deployment.Application.MaintenancePiece::radioRemove
0x183a2  ldarg.0
0x183a3  ldftn    instance void System.Deployment.Application.MaintenancePiece::radioRemove_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x183a9  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x183ae  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x183b3  ldloc.0
0x183b4  ldarg.0
0x183b5  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.MaintenancePiece::groupRule
0x183ba  ldstr    aGrouprule// "groupRule"
0x183bf  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x183c4  ldarg.0
0x183c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.MaintenancePiece::groupRule
0x183ca  ldc.i4.0
0x183cb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32)
0x183d0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x183d5  ldarg.0
0x183d6  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.MaintenancePiece::groupRule
0x183db  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_ControlDark()
0x183e0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x183e5  ldarg.0
0x183e6  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.MaintenancePiece::groupRule
0x183eb  ldc.i4.0
0x183ec  callvirt instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x183f1  ldarg.0
0x183f2  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.MaintenancePiece::groupRule
0x183f7  ldstr    aGrouprule// "groupRule"
0x183fc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x18401  ldarg.0
0x18402  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.MaintenancePiece::groupRule
0x18407  ldc.i4.0
0x18408  callvirt instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::set_TabStop(bool)
0x1840d  ldloc.0
0x1840e  ldarg.0
0x1840f  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.MaintenancePiece::groupDivider
0x18414  ldstr    aGroupdivider// "groupDivider"
0x18419  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1841e  ldarg.0
0x1841f  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.MaintenancePiece::groupDivider
0x18424  ldc.i4.0
0x18425  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x1842a  ldc.i4.0
0x1842b  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x18430  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x18435  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x1843a  ldarg.0
0x1843b  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.MaintenancePiece::groupDivider
0x18440  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_ControlDark()
0x18445  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x1844a  ldarg.0
0x1844b  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.MaintenancePiece::groupDivider
0x18450  ldc.i4.0
0x18451  callvirt instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x18456  ldarg.0
0x18457  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.MaintenancePiece::groupDivider
0x1845c  ldstr    aGroupdivider// "groupDivider"
0x18461  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x18466  ldarg.0
0x18467  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.MaintenancePiece::groupDivider
0x1846c  ldc.i4.0
0x1846d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::set_TabStop(bool)
0x18472  ldloc.0
0x18473  ldarg.0
0x18474  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.MaintenancePiece::btnOk
0x18479  ldstr    aBtnok// "btnOk"
0x1847e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x18483  ldarg.0
0x18484  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.MaintenancePiece::btnOk
0x18489  ldc.i4.0
0x1848a  ldc.i4.0
0x1848b  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits4
0x18490  ldc.i4.0
0x18491  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x18496  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x1849b  ldarg.0
0x1849c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.MaintenancePiece::btnOk
0x184a1  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumButtonSizeWidth
0x184a6  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumButtonSizeHeight
0x184ab  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x184b0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x184b5  ldarg.0
0x184b6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.MaintenancePiece::btnOk
0x184bb  ldstr    aBtnok// "btnOk"
0x184c0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x184c5  ldarg.0
0x184c6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.MaintenancePiece::btnOk
0x184cb  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits10
0x184d0  ldc.i4.0
0x184d1  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits10
0x184d6  ldc.i4.0
0x184d7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x184dc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Padding(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x184e1  ldarg.0
  ... truncated ...
```
