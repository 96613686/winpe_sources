# System.Deployment.Application.ProgressPiece::InitializeComponent

- ea: `0x1ca30`
- end: `0x1d23a`
- name: `System.Deployment.Application.ProgressPiece::InitializeComponent`
- size: `2058`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1c780`

## callees

- `0x9d0`
- `0x1ca30`
- `0x23020`

## string_xrefs

- `0x1cce0`: `linkAppId`
- `0x1ccfc`: `linkAppId`

## pseudocode

```c

```

## disassembly

```asm
0x1ca30  ldtoken  System.Deployment.Application.ProgressPiece
0x1ca35  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ca3a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x1ca3f  stloc.0
0x1ca40  ldarg.0
0x1ca41  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x1ca46  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ProgressPiece::topTextTableLayoutPanel
0x1ca4b  ldarg.0
0x1ca4c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0x1ca51  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ProgressPiece::pictureDesktop
0x1ca56  ldarg.0
0x1ca57  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1ca5c  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblSubHeader
0x1ca61  ldarg.0
0x1ca62  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1ca67  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblHeader
0x1ca6c  ldarg.0
0x1ca6d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0x1ca72  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ProgressPiece::pictureAppIcon
0x1ca77  ldarg.0
0x1ca78  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1ca7d  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblApplication
0x1ca82  ldarg.0
0x1ca83  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::.ctor()
0x1ca88  stfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.ProgressPiece::linkAppId
0x1ca8d  ldarg.0
0x1ca8e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1ca93  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblFrom
0x1ca98  ldarg.0
0x1ca99  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1ca9e  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblFromId
0x1caa3  ldarg.0
0x1caa4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ProgressBar::.ctor()
0x1caa9  stfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar System.Deployment.Application.ProgressPiece::progress
0x1caae  ldarg.0
0x1caaf  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1cab4  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblProgressText
0x1cab9  ldarg.0
0x1caba  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x1cabf  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.ProgressPiece::groupRule
0x1cac4  ldarg.0
0x1cac5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x1caca  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.ProgressPiece::groupDivider
0x1cacf  ldarg.0
0x1cad0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x1cad5  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.ProgressPiece::btnCancel
0x1cada  ldarg.0
0x1cadb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x1cae0  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ProgressPiece::overarchingTableLayoutPanel
0x1cae5  ldarg.0
0x1cae6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x1caeb  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ProgressPiece::contentTableLayoutPanel
0x1caf0  ldarg.0
0x1caf1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ProgressPiece::topTextTableLayoutPanel
0x1caf6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x1cafb  ldarg.0
0x1cafc  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ProgressPiece::pictureDesktop
0x1cb01  callvirt instance void [System]System.ComponentModel.ISupportInitialize::BeginInit()
0x1cb06  ldarg.0
0x1cb07  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ProgressPiece::pictureAppIcon
0x1cb0c  callvirt instance void [System]System.ComponentModel.ISupportInitialize::BeginInit()
0x1cb11  ldarg.0
0x1cb12  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ProgressPiece::overarchingTableLayoutPanel
0x1cb17  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x1cb1c  ldarg.0
0x1cb1d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ProgressPiece::contentTableLayoutPanel
0x1cb22  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x1cb27  ldarg.0
0x1cb28  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x1cb2d  ldloc.0
0x1cb2e  ldarg.0
0x1cb2f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ProgressPiece::topTextTableLayoutPanel
0x1cb34  ldstr    aToptexttablela// "topTextTableLayoutPanel"
0x1cb39  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1cb3e  ldarg.0
0x1cb3f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ProgressPiece::topTextTableLayoutPanel
0x1cb44  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Window()
0x1cb49  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x1cb4e  ldarg.0
0x1cb4f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ProgressPiece::topTextTableLayoutPanel
0x1cb54  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x1cb59  ldarg.0
0x1cb5a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblHeader
0x1cb5f  ldc.i4.0
0x1cb60  ldc.i4.0
0x1cb61  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x1cb66  ldarg.0
0x1cb67  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ProgressPiece::topTextTableLayoutPanel
0x1cb6c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x1cb71  ldarg.0
0x1cb72  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblSubHeader
0x1cb77  ldc.i4.0
0x1cb78  ldc.i4.1
0x1cb79  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x1cb7e  ldarg.0
0x1cb7f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ProgressPiece::topTextTableLayoutPanel
0x1cb84  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x1cb89  ldarg.0
0x1cb8a  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ProgressPiece::pictureDesktop
0x1cb8f  ldc.i4.1
0x1cb90  ldc.i4.0
0x1cb91  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x1cb96  ldarg.0
0x1cb97  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ProgressPiece::topTextTableLayoutPanel
0x1cb9c  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits498
0x1cba1  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits61
0x1cba6  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x1cbab  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x1cbb0  ldarg.0
0x1cbb1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ProgressPiece::topTextTableLayoutPanel
0x1cbb6  ldstr    aToptexttablela// "topTextTableLayoutPanel"
0x1cbbb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1cbc0  ldloc.0
0x1cbc1  ldarg.0
0x1cbc2  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ProgressPiece::pictureDesktop
0x1cbc7  ldstr    aPicturedesktop// "pictureDesktop"
0x1cbcc  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1cbd1  ldarg.0
0x1cbd2  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ProgressPiece::pictureDesktop
0x1cbd7  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits61
0x1cbdc  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits61
0x1cbe1  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x1cbe6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x1cbeb  ldarg.0
0x1cbec  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ProgressPiece::pictureDesktop
0x1cbf1  ldstr    aPicturedesktop// "pictureDesktop"
0x1cbf6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1cbfb  ldarg.0
0x1cbfc  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ProgressPiece::topTextTableLayoutPanel
0x1cc01  ldarg.0
0x1cc02  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ProgressPiece::pictureDesktop
0x1cc07  ldc.i4.2
0x1cc08  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetRowSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x1cc0d  ldarg.0
0x1cc0e  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ProgressPiece::pictureDesktop
0x1cc13  ldc.i4.0
0x1cc14  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_TabStop(bool)
0x1cc19  ldarg.0
0x1cc1a  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ProgressPiece::pictureDesktop
0x1cc1f  ldc.i4.2
0x1cc20  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_SizeMode(valuetype [System.Windows.Forms]System.Windows.Forms.PictureBoxSizeMode)
0x1cc25  ldloc.0
0x1cc26  ldarg.0
0x1cc27  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblSubHeader
0x1cc2c  ldstr    aLblsubheader// "lblSubHeader"
0x1cc31  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1cc36  ldarg.0
0x1cc37  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblSubHeader
0x1cc3c  ldstr    aLblsubheader// "lblSubHeader"
0x1cc41  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1cc46  ldloc.0
0x1cc47  ldarg.0
0x1cc48  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblHeader
0x1cc4d  ldstr    aLblheader// "lblHeader"
0x1cc52  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1cc57  ldarg.0
0x1cc58  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblHeader
0x1cc5d  ldc.i4.1
0x1cc5e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_AutoEllipsis(bool)
0x1cc63  ldarg.0
0x1cc64  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblHeader
0x1cc69  ldstr    aLblheader// "lblHeader"
0x1cc6e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1cc73  ldarg.0
0x1cc74  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblHeader
0x1cc79  ldc.i4.0
0x1cc7a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_UseMnemonic(bool)
0x1cc7f  ldloc.0
0x1cc80  ldarg.0
0x1cc81  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ProgressPiece::pictureAppIcon
0x1cc86  ldstr    aPictureappicon// "pictureAppIcon"
0x1cc8b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1cc90  ldarg.0
0x1cc91  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ProgressPiece::pictureAppIcon
0x1cc96  ldstr    aPictureappicon// "pictureAppIcon"
0x1cc9b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1cca0  ldarg.0
0x1cca1  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ProgressPiece::pictureAppIcon
0x1cca6  ldc.i4.0
0x1cca7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_TabStop(bool)
0x1ccac  ldarg.0
0x1ccad  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ProgressPiece::pictureAppIcon
0x1ccb2  ldc.i4.2
0x1ccb3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_SizeMode(valuetype [System.Windows.Forms]System.Windows.Forms.PictureBoxSizeMode)
0x1ccb8  ldloc.0
0x1ccb9  ldarg.0
0x1ccba  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblApplication
0x1ccbf  ldstr    aLblapplication// "lblApplication"
0x1ccc4  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1ccc9  ldarg.0
0x1ccca  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblApplication
0x1cccf  ldstr    aLblapplication// "lblApplication"
0x1ccd4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1ccd9  ldloc.0
0x1ccda  ldarg.0
0x1ccdb  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.ProgressPiece::linkAppId
0x1cce0  ldstr    aLinkappid// "linkAppId"
0x1cce5  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1ccea  ldarg.0
0x1cceb  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.ProgressPiece::linkAppId
0x1ccf0  ldc.i4.1
0x1ccf1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_AutoEllipsis(bool)
0x1ccf6  ldarg.0
0x1ccf7  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.ProgressPiece::linkAppId
0x1ccfc  ldstr    aLinkappid// "linkAppId"
0x1cd01  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1cd06  ldarg.0
0x1cd07  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.ProgressPiece::linkAppId
0x1cd0c  ldc.i4.0
0x1cd0d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_UseMnemonic(bool)
0x1cd12  ldarg.0
0x1cd13  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.ProgressPiece::linkAppId
0x1cd18  ldarg.0
0x1cd19  ldftn    instance void System.Deployment.Application.ProgressPiece::linkAppId_LinkClicked(object sender, class [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventArgs e)
0x1cd1f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventHandler::.ctor(object, native int)
0x1cd24  callvirt instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::add_LinkClicked(class [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventHandler)
0x1cd29  ldloc.0
0x1cd2a  ldarg.0
0x1cd2b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblFrom
0x1cd30  ldstr    aLblfrom// "lblFrom"
0x1cd35  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1cd3a  ldarg.0
0x1cd3b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblFrom
0x1cd40  ldstr    aLblfrom// "lblFrom"
0x1cd45  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1cd4a  ldloc.0
0x1cd4b  ldarg.0
0x1cd4c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblFromId
0x1cd51  ldstr    aLblfromid// "lblFromId"
0x1cd56  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1cd5b  ldarg.0
0x1cd5c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblFromId
0x1cd61  ldc.i4.1
0x1cd62  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_AutoEllipsis(bool)
0x1cd67  ldarg.0
0x1cd68  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblFromId
0x1cd6d  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits384
0x1cd72  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits32
0x1cd77  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x1cd7c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x1cd81  ldarg.0
0x1cd82  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblFromId
0x1cd87  ldstr    aLblfromid// "lblFromId"
0x1cd8c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1cd91  ldarg.0
0x1cd92  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblFromId
0x1cd97  ldc.i4.0
0x1cd98  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_UseMnemonic(bool)
0x1cd9d  ldloc.0
0x1cd9e  ldarg.0
0x1cd9f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar System.Deployment.Application.ProgressPiece::progress
0x1cda4  ldstr    aProgress// "progress"
0x1cda9  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1cdae  ldarg.0
0x1cdaf  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ProgressPiece::contentTableLayoutPanel
0x1cdb4  ldarg.0
0x1cdb5  ldfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar System.Deployment.Application.ProgressPiece::progress
0x1cdba  ldc.i4.2
0x1cdbb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x1cdc0  ldarg.0
0x1cdc1  ldfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar System.Deployment.Application.ProgressPiece::progress
0x1cdc6  ldstr    aProgress// "progress"
0x1cdcb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1cdd0  ldarg.0
0x1cdd1  ldfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar System.Deployment.Application.ProgressPiece::progress
0x1cdd6  ldc.i4.0
0x1cdd7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ProgressBar::set_TabStop(bool)
0x1cddc  ldarg.0
0x1cddd  ldfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar System.Deployment.Application.ProgressPiece::progress
0x1cde2  ldarg.0
0x1cde3  ldarg.0
0x1cde4  ldfld    class [System.Windows.Forms]System.Windows.Forms.ProgressBar System.Deployment.Application.ProgressPiece::progress
0x1cde9  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Height()
0x1cdee  call     instance int32 [System.Windows.Forms]System.Windows.Forms.Control::LogicalToDeviceUnits(int32)
0x1cdf3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Height(int32)
0x1cdf8  ldloc.0
0x1cdf9  ldarg.0
0x1cdfa  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblProgressText
0x1cdff  ldstr    aLblprogresstex// "lblProgressText"
0x1ce04  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1ce09  ldarg.0
0x1ce0a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ProgressPiece::contentTableLayoutPanel
0x1ce0f  ldarg.0
0x1ce10  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblProgressText
0x1ce15  ldc.i4.2
0x1ce16  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x1ce1b  ldarg.0
0x1ce1c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ProgressPiece::lblProgressText
0x1ce21  ldstr    aLblprogresstex// "lblProgressText"
0x1ce26  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1ce2b  ldloc.0
0x1ce2c  ldarg.0
0x1ce2d  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.ProgressPiece::groupRule
0x1ce32  ldstr    aGrouprule// "groupRule"
0x1ce37  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1ce3c  ldarg.0
0x1ce3d  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Deployment.Application.ProgressPiece::groupRule
0x1ce42  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_ControlDark()
0x1ce47  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x1ce4c  ldarg.0
  ... truncated ...
```
