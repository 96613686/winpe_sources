# Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::InitializeComponent

- ea: `0x21e80`
- end: `0x22735`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::InitializeComponent`
- size: `2229`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x20b30`

## callees

- `0x130e0`
- `0x13250`

## string_xrefs

- `0x22129`: `lblAccessed`
- `0x22139`: `lblAccessed`
- `0x22156`: `txtChannelPath`
- `0x22166`: `txtChannelPath`
- `0x221a4`: `ChannelPathLabel`
- `0x221b4`: `ChannelPathLabel`
- `0x221c5`: `lblCreated`
- `0x221d5`: `lblCreated`
- `0x221e6`: `FilePathLabel`
- `0x221f6`: `FilePathLabel`
- `0x22259`: `txtFilePath`
- `0x22269`: `txtFilePath`
- `0x2234a`: `btnSecurity`
- `0x2235a`: `btnSecurity`
- `0x22432`: `rdOverWriteNeed`
- `0x22442`: `rdOverWriteNeed`
- `0x2247c`: `rdNoOverwrite`
- `0x2248c`: `rdNoOverwrite`

## pseudocode

```c

```

## disassembly

```asm
0x21e80  ldarg.0
0x21e81  newobj   instance void [System]System.ComponentModel.Container::.ctor()
0x21e86  stfld    class [System]System.ComponentModel.IContainer Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::components
0x21e8b  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties
0x21e90  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21e95  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x21e9a  stloc.0
0x21e9b  ldarg.0
0x21e9c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x21ea1  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::tbTop
0x21ea6  ldarg.0
0x21ea7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x21eac  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::lblAccessed
0x21eb1  ldarg.0
0x21eb2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x21eb7  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::txtChannelPath
0x21ebc  ldarg.0
0x21ebd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x21ec2  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::lblModified
0x21ec7  ldarg.0
0x21ec8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x21ecd  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::ChannelPathLabel
0x21ed2  ldarg.0
0x21ed3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x21ed8  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::lblCreated
0x21edd  ldarg.0
0x21ede  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x21ee3  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::FilePathLabel
0x21ee8  ldarg.0
0x21ee9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x21eee  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::lblSize
0x21ef3  ldarg.0
0x21ef4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x21ef9  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::label1
0x21efe  ldarg.0
0x21eff  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x21f04  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::txtFilePath
0x21f09  ldarg.0
0x21f0a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x21f0f  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::label3
0x21f14  ldarg.0
0x21f15  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x21f1a  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::label5
0x21f1f  ldarg.0
0x21f20  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x21f25  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::label4
0x21f2a  ldarg.0
0x21f2b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x21f30  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::chkEnable
0x21f35  ldarg.0
0x21f36  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x21f3b  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::btnSecurity
0x21f40  ldarg.0
0x21f41  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x21f46  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::btnClearLog
0x21f4b  ldarg.0
0x21f4c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x21f51  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::label10
0x21f56  ldarg.0
0x21f57  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x21f5c  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::rdArchive
0x21f61  ldarg.0
0x21f62  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x21f67  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::rdOverWriteNeed
0x21f6c  ldarg.0
0x21f6d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x21f72  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::rdNoOverwrite
0x21f77  ldarg.0
0x21f78  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x21f7d  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::tableBottom
0x21f82  ldarg.0
0x21f83  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x21f88  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::label9
0x21f8d  ldarg.0
0x21f8e  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.CustomNumericUpDown::.ctor()
0x21f93  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.CustomNumericUpDown Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::maxLogSize
0x21f98  ldarg.0
0x21f99  ldarg.0
0x21f9a  ldfld    class [System]System.ComponentModel.IContainer Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::components
0x21f9f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolTip::.ctor(class [System]System.ComponentModel.IContainer)
0x21fa4  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolTip Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::toolTip1
0x21fa9  ldarg.0
0x21faa  ldarg.0
0x21fab  ldfld    class [System]System.ComponentModel.IContainer Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::components
0x21fb0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.NotifyIcon::.ctor(class [System]System.ComponentModel.IContainer)
0x21fb5  stfld    class [System.Windows.Forms]System.Windows.Forms.NotifyIcon Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::notifyIcon1
0x21fba  ldarg.0
0x21fbb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::tbTop
0x21fc0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x21fc5  ldarg.0
0x21fc6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::tableBottom
0x21fcb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x21fd0  ldarg.0
0x21fd1  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.CustomNumericUpDown Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::maxLogSize
0x21fd6  callvirt instance void [System]System.ComponentModel.ISupportInitialize::BeginInit()
0x21fdb  ldarg.0
0x21fdc  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x21fe1  ldloc.0
0x21fe2  ldarg.0
0x21fe3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::tbTop
0x21fe8  ldstr    aTbtop// "tbTop"
0x21fed  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x21ff2  ldarg.0
0x21ff3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::tbTop
0x21ff8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x21ffd  ldarg.0
0x21ffe  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::lblAccessed
0x22003  ldc.i4.1
0x22004  ldc.i4.5
0x22005  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x2200a  ldarg.0
0x2200b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::tbTop
0x22010  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x22015  ldarg.0
0x22016  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::txtChannelPath
0x2201b  ldc.i4.1
0x2201c  ldc.i4.0
0x2201d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x22022  ldarg.0
0x22023  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::tbTop
0x22028  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x2202d  ldarg.0
0x2202e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::lblModified
0x22033  ldc.i4.1
0x22034  ldc.i4.4
0x22035  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x2203a  ldarg.0
0x2203b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::tbTop
0x22040  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x22045  ldarg.0
0x22046  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::ChannelPathLabel
0x2204b  ldc.i4.0
0x2204c  ldc.i4.0
0x2204d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x22052  ldarg.0
0x22053  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::tbTop
0x22058  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x2205d  ldarg.0
0x2205e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::lblCreated
0x22063  ldc.i4.1
0x22064  ldc.i4.3
0x22065  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x2206a  ldarg.0
0x2206b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::tbTop
0x22070  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x22075  ldarg.0
0x22076  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::FilePathLabel
0x2207b  ldc.i4.0
0x2207c  ldc.i4.1
0x2207d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x22082  ldarg.0
0x22083  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::tbTop
0x22088  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x2208d  ldarg.0
0x2208e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::lblSize
0x22093  ldc.i4.1
0x22094  ldc.i4.2
0x22095  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x2209a  ldarg.0
0x2209b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::tbTop
0x220a0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x220a5  ldarg.0
0x220a6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::label1
0x220ab  ldc.i4.0
0x220ac  ldc.i4.2
0x220ad  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x220b2  ldarg.0
0x220b3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::tbTop
0x220b8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x220bd  ldarg.0
0x220be  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::txtFilePath
0x220c3  ldc.i4.1
0x220c4  ldc.i4.1
0x220c5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x220ca  ldarg.0
0x220cb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::tbTop
0x220d0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x220d5  ldarg.0
0x220d6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::label3
0x220db  ldc.i4.0
0x220dc  ldc.i4.3
0x220dd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x220e2  ldarg.0
0x220e3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::tbTop
0x220e8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x220ed  ldarg.0
0x220ee  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::label5
0x220f3  ldc.i4.0
0x220f4  ldc.i4.5
0x220f5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x220fa  ldarg.0
0x220fb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::tbTop
0x22100  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x22105  ldarg.0
0x22106  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::label4
0x2210b  ldc.i4.0
0x2210c  ldc.i4.4
0x2210d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x22112  ldarg.0
0x22113  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::tbTop
0x22118  ldstr    aTbtop// "tbTop"
0x2211d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x22122  ldloc.0
0x22123  ldarg.0
0x22124  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::lblAccessed
0x22129  ldstr    aLblaccessed// "lblAccessed"
0x2212e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x22133  ldarg.0
0x22134  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::lblAccessed
0x22139  ldstr    aLblaccessed// "lblAccessed"
0x2213e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x22143  ldarg.0
0x22144  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::txtChannelPath
0x22149  ldc.i4.0
0x2214a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBoxBase::set_BorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.BorderStyle)
0x2214f  ldloc.0
0x22150  ldarg.0
0x22151  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::txtChannelPath
0x22156  ldstr    aTxtchannelpath// "txtChannelPath"
0x2215b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x22160  ldarg.0
0x22161  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::txtChannelPath
0x22166  ldstr    aTxtchannelpath// "txtChannelPath"
0x2216b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x22170  ldarg.0
0x22171  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::txtChannelPath
0x22176  ldc.i4.1
0x22177  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBoxBase::set_ReadOnly(bool)
0x2217c  ldloc.0
0x2217d  ldarg.0
0x2217e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::lblModified
0x22183  ldstr    aLblmodified// "lblModified"
0x22188  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x2218d  ldarg.0
0x2218e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::lblModified
0x22193  ldstr    aLblmodified// "lblModified"
0x22198  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2219d  ldloc.0
0x2219e  ldarg.0
0x2219f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::ChannelPathLabel
0x221a4  ldstr    aChannelpathlab// "ChannelPathLabel"
0x221a9  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x221ae  ldarg.0
0x221af  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::ChannelPathLabel
0x221b4  ldstr    aChannelpathlab// "ChannelPathLabel"
0x221b9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x221be  ldloc.0
0x221bf  ldarg.0
0x221c0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::lblCreated
0x221c5  ldstr    aLblcreated// "lblCreated"
0x221ca  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x221cf  ldarg.0
0x221d0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::lblCreated
0x221d5  ldstr    aLblcreated// "lblCreated"
0x221da  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x221df  ldloc.0
0x221e0  ldarg.0
0x221e1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::FilePathLabel
0x221e6  ldstr    aFilepathlabel// "FilePathLabel"
0x221eb  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x221f0  ldarg.0
0x221f1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::FilePathLabel
0x221f6  ldstr    aFilepathlabel// "FilePathLabel"
0x221fb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x22200  ldloc.0
0x22201  ldarg.0
0x22202  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::lblSize
0x22207  ldstr    aLblsize// "lblSize"
0x2220c  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x22211  ldarg.0
0x22212  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::lblSize
0x22217  ldstr    aLblsize// "lblSize"
0x2221c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x22221  ldloc.0
0x22222  ldarg.0
0x22223  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::label1
0x22228  ldstr    aLabel1// "label1"
0x2222d  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x22232  ldarg.0
0x22233  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::label1
0x22238  ldstr    aLabel1// "label1"
0x2223d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x22242  ldarg.0
0x22243  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::txtFilePath
0x22248  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Window()
0x2224d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x22252  ldloc.0
0x22253  ldarg.0
0x22254  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::txtFilePath
0x22259  ldstr    aTxtfilepath// "txtFilePath"
0x2225e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x22263  ldarg.0
0x22264  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::txtFilePath
0x22269  ldstr    aTxtfilepath// "txtFilePath"
0x2226e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x22273  ldloc.0
0x22274  ldarg.0
0x22275  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ChannelProperties::label3
0x2227a  ldstr    aLabel3// "label3"
0x2227f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
  ... truncated ...
```
