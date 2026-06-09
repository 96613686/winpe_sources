# System.Deployment.Application.UpdatePiece::InitializeComponent

- ea: `0x20c60`
- end: `0x2177e`
- name: `System.Deployment.Application.UpdatePiece::InitializeComponent`
- size: `2846`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x20b50`

## callees

- `0x9d0`
- `0x20c60`
- `0x23020`

## string_xrefs

- `0x20f67`: `linkAppId`
- `0x20f9f`: `linkAppId`
- `0x216ff`: `UpdatePiece`

## pseudocode

```c

```

## disassembly

```asm
0x20c60  ldtoken  System.Deployment.Application.UpdatePiece
0x20c65  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20c6a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x20c6f  stloc.0
0x20c70  ldarg.0
0x20c71  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x20c76  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::descriptionTableLayoutPanel
0x20c7b  ldarg.0
0x20c7c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0x20c81  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.UpdatePiece::pictureDesktop
0x20c86  ldarg.0
0x20c87  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x20c8c  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblSubHeader
0x20c91  ldarg.0
0x20c92  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x20c97  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblHeader
0x20c9c  ldarg.0
0x20c9d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x20ca2  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblApplication
0x20ca7  ldarg.0
0x20ca8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::.ctor()
0x20cad  stfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.UpdatePiece::linkAppId
0x20cb2  ldarg.0
0x20cb3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x20cb8  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblFrom
0x20cbd  ldarg.0
0x20cbe  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x20cc3  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblFromId
0x20cc8  ldarg.0
0x20cc9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x20cce  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.UpdatePiece::groupRule
0x20cd3  ldarg.0
0x20cd4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x20cd9  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.UpdatePiece::groupDivider
0x20cde  ldarg.0
0x20cdf  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x20ce4  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.UpdatePiece::btnOk
0x20ce9  ldarg.0
0x20cea  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x20cef  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.UpdatePiece::btnSkip
0x20cf4  ldarg.0
0x20cf5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x20cfa  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::contentTableLayoutPanel
0x20cff  ldarg.0
0x20d00  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x20d05  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::okSkipTableLayoutPanel
0x20d0a  ldarg.0
0x20d0b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x20d10  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::overarchingTableLayoutPanel
0x20d15  ldarg.0
0x20d16  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::descriptionTableLayoutPanel
0x20d1b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x20d20  ldarg.0
0x20d21  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.UpdatePiece::pictureDesktop
0x20d26  callvirt instance void [System]System.ComponentModel.ISupportInitialize::BeginInit()
0x20d2b  ldarg.0
0x20d2c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::contentTableLayoutPanel
0x20d31  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x20d36  ldarg.0
0x20d37  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::okSkipTableLayoutPanel
0x20d3c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x20d41  ldarg.0
0x20d42  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::overarchingTableLayoutPanel
0x20d47  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x20d4c  ldarg.0
0x20d4d  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x20d52  ldloc.0
0x20d53  ldarg.0
0x20d54  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::descriptionTableLayoutPanel
0x20d59  ldstr    aDescriptiontab// "descriptionTableLayoutPanel"
0x20d5e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x20d63  ldarg.0
0x20d64  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::descriptionTableLayoutPanel
0x20d69  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Window()
0x20d6e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x20d73  ldarg.0
0x20d74  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::descriptionTableLayoutPanel
0x20d79  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0x20d7e  ldc.i4.0
0x20d7f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType)
0x20d84  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0x20d89  pop
0x20d8a  ldarg.0
0x20d8b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::descriptionTableLayoutPanel
0x20d90  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0x20d95  ldc.i4.0
0x20d96  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType)
0x20d9b  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0x20da0  pop
0x20da1  ldarg.0
0x20da2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::descriptionTableLayoutPanel
0x20da7  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x20dac  ldarg.0
0x20dad  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.UpdatePiece::pictureDesktop
0x20db2  ldc.i4.1
0x20db3  ldc.i4.0
0x20db4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x20db9  ldarg.0
0x20dba  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::descriptionTableLayoutPanel
0x20dbf  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x20dc4  ldarg.0
0x20dc5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblSubHeader
0x20dca  ldc.i4.0
0x20dcb  ldc.i4.1
0x20dcc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x20dd1  ldarg.0
0x20dd2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::descriptionTableLayoutPanel
0x20dd7  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x20ddc  ldarg.0
0x20ddd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblHeader
0x20de2  ldc.i4.0
0x20de3  ldc.i4.0
0x20de4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x20de9  ldarg.0
0x20dea  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::descriptionTableLayoutPanel
0x20def  ldc.i4.0
0x20df0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32)
0x20df5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x20dfa  ldarg.0
0x20dfb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::descriptionTableLayoutPanel
0x20e00  ldstr    aDescriptiontab// "descriptionTableLayoutPanel"
0x20e05  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x20e0a  ldarg.0
0x20e0b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::descriptionTableLayoutPanel
0x20e10  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0x20e15  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor()
0x20e1a  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0x20e1f  pop
0x20e20  ldarg.0
0x20e21  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::descriptionTableLayoutPanel
0x20e26  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0x20e2b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor()
0x20e30  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0x20e35  pop
0x20e36  ldloc.0
0x20e37  ldarg.0
0x20e38  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.UpdatePiece::pictureDesktop
0x20e3d  ldstr    aPicturedesktop// "pictureDesktop"
0x20e42  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x20e47  ldarg.0
0x20e48  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.UpdatePiece::pictureDesktop
0x20e4d  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x20e52  ldc.i4.0
0x20e53  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x20e58  ldc.i4.0
0x20e59  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x20e5e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x20e63  ldarg.0
0x20e64  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.UpdatePiece::pictureDesktop
0x20e69  ldstr    aPicturedesktop// "pictureDesktop"
0x20e6e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x20e73  ldarg.0
0x20e74  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.UpdatePiece::descriptionTableLayoutPanel
0x20e79  ldarg.0
0x20e7a  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.UpdatePiece::pictureDesktop
0x20e7f  ldc.i4.2
0x20e80  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetRowSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x20e85  ldarg.0
0x20e86  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.UpdatePiece::pictureDesktop
0x20e8b  ldc.i4.0
0x20e8c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_TabStop(bool)
0x20e91  ldarg.0
0x20e92  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.UpdatePiece::pictureDesktop
0x20e97  ldc.i4.2
0x20e98  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_SizeMode(valuetype [System.Windows.Forms]System.Windows.Forms.PictureBoxSizeMode)
0x20e9d  ldloc.0
0x20e9e  ldarg.0
0x20e9f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblSubHeader
0x20ea4  ldstr    aLblsubheader// "lblSubHeader"
0x20ea9  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x20eae  ldarg.0
0x20eaf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblSubHeader
0x20eb4  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits29
0x20eb9  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x20ebe  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x20ec3  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits8
0x20ec8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x20ecd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x20ed2  ldarg.0
0x20ed3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblSubHeader
0x20ed8  ldstr    aLblsubheader// "lblSubHeader"
0x20edd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x20ee2  ldloc.0
0x20ee3  ldarg.0
0x20ee4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblHeader
0x20ee9  ldstr    aLblheader// "lblHeader"
0x20eee  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x20ef3  ldarg.0
0x20ef4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblHeader
0x20ef9  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits10
0x20efe  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits11
0x20f03  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x20f08  ldc.i4.0
0x20f09  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x20f0e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x20f13  ldarg.0
0x20f14  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblHeader
0x20f19  ldstr    aLblheader// "lblHeader"
0x20f1e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x20f23  ldloc.0
0x20f24  ldarg.0
0x20f25  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblApplication
0x20f2a  ldstr    aLblapplication// "lblApplication"
0x20f2f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x20f34  ldarg.0
0x20f35  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblApplication
0x20f3a  ldc.i4.0
0x20f3b  ldc.i4.0
0x20f3c  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x20f41  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x20f46  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x20f4b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x20f50  ldarg.0
0x20f51  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblApplication
0x20f56  ldstr    aLblapplication// "lblApplication"
0x20f5b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x20f60  ldloc.0
0x20f61  ldarg.0
0x20f62  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.UpdatePiece::linkAppId
0x20f67  ldstr    aLinkappid// "linkAppId"
0x20f6c  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x20f71  ldarg.0
0x20f72  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.UpdatePiece::linkAppId
0x20f77  ldc.i4.1
0x20f78  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_AutoEllipsis(bool)
0x20f7d  ldarg.0
0x20f7e  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.UpdatePiece::linkAppId
0x20f83  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x20f88  ldc.i4.0
0x20f89  ldc.i4.0
0x20f8a  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x20f8f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x20f94  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x20f99  ldarg.0
0x20f9a  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.UpdatePiece::linkAppId
0x20f9f  ldstr    aLinkappid// "linkAppId"
0x20fa4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x20fa9  ldarg.0
0x20faa  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.UpdatePiece::linkAppId
0x20faf  ldc.i4.1
0x20fb0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::set_TabStop(bool)
0x20fb5  ldarg.0
0x20fb6  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.UpdatePiece::linkAppId
0x20fbb  ldc.i4.0
0x20fbc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_UseMnemonic(bool)
0x20fc1  ldarg.0
0x20fc2  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.UpdatePiece::linkAppId
0x20fc7  ldarg.0
0x20fc8  ldftn    instance void System.Deployment.Application.UpdatePiece::linkAppId_LinkClicked(object sender, class [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventArgs e)
0x20fce  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventHandler::.ctor(object, native int)
0x20fd3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::add_LinkClicked(class [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventHandler)
0x20fd8  ldloc.0
0x20fd9  ldarg.0
0x20fda  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblFrom
0x20fdf  ldstr    aLblfrom// "lblFrom"
0x20fe4  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x20fe9  ldarg.0
0x20fea  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblFrom
0x20fef  ldc.i4.0
0x20ff0  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x20ff5  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x20ffa  ldc.i4.0
0x20ffb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x21000  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x21005  ldarg.0
0x21006  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblFrom
0x2100b  ldstr    aLblfrom// "lblFrom"
0x21010  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x21015  ldloc.0
0x21016  ldarg.0
0x21017  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblFromId
0x2101c  ldstr    aLblfromid// "lblFromId"
0x21021  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x21026  ldarg.0
0x21027  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblFromId
0x2102c  ldc.i4.1
0x2102d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_AutoEllipsis(bool)
0x21032  ldarg.0
0x21033  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblFromId
0x21038  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x2103d  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x21042  ldc.i4.0
0x21043  ldc.i4.0
0x21044  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x21049  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x2104e  ldarg.0
0x2104f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblFromId
0x21054  ldstr    aLblfromid// "lblFromId"
0x21059  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2105e  ldarg.0
0x2105f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.UpdatePiece::lblFromId
0x21064  ldc.i4.0
0x21065  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_UseMnemonic(bool)
0x2106a  ldloc.0
0x2106b  ldarg.0
0x2106c  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.UpdatePiece::groupRule
0x21071  ldstr    aGrouprule// "groupRule"
0x21076  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x2107b  ldarg.0
0x2107c  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.UpdatePiece::groupRule
  ... truncated ...
```
