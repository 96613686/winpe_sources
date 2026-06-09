# System.Deployment.Application.PlatformPiece::InitializeComponent

- ea: `0x1c250`
- end: `0x1c503`
- name: `System.Deployment.Application.PlatformPiece::InitializeComponent`
- size: `691`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1c1c0`

## string_xrefs

- `0x1c3be`: `linkSupport`
- `0x1c3ce`: `linkSupport`

## pseudocode

```c

```

## disassembly

```asm
0x1c250  ldtoken  System.Deployment.Application.PlatformPiece
0x1c255  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c25a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x1c25f  stloc.0
0x1c260  ldarg.0
0x1c261  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1c266  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.PlatformPiece::lblMessage
0x1c26b  ldarg.0
0x1c26c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0x1c271  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.PlatformPiece::pictureIcon
0x1c276  ldarg.0
0x1c277  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x1c27c  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.PlatformPiece::btnOk
0x1c281  ldarg.0
0x1c282  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::.ctor()
0x1c287  stfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.PlatformPiece::linkSupport
0x1c28c  ldarg.0
0x1c28d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x1c292  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.PlatformPiece::overarchingTableLayoutPanel
0x1c297  ldarg.0
0x1c298  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.PlatformPiece::pictureIcon
0x1c29d  callvirt instance void [System]System.ComponentModel.ISupportInitialize::BeginInit()
0x1c2a2  ldarg.0
0x1c2a3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.PlatformPiece::overarchingTableLayoutPanel
0x1c2a8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x1c2ad  ldarg.0
0x1c2ae  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x1c2b3  ldloc.0
0x1c2b4  ldarg.0
0x1c2b5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.PlatformPiece::lblMessage
0x1c2ba  ldstr    aLblmessage// "lblMessage"
0x1c2bf  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1c2c4  ldarg.0
0x1c2c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.PlatformPiece::lblMessage
0x1c2ca  ldstr    aLblmessage// "lblMessage"
0x1c2cf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1c2d4  ldloc.0
0x1c2d5  ldarg.0
0x1c2d6  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.PlatformPiece::pictureIcon
0x1c2db  ldstr    aPictureicon// "pictureIcon"
0x1c2e0  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1c2e5  ldarg.0
0x1c2e6  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.PlatformPiece::pictureIcon
0x1c2eb  ldstr    aPictureicon// "pictureIcon"
0x1c2f0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1c2f5  ldarg.0
0x1c2f6  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.PlatformPiece::pictureIcon
0x1c2fb  ldc.i4.0
0x1c2fc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_TabStop(bool)
0x1c301  ldarg.0
0x1c302  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.PlatformPiece::pictureIcon
0x1c307  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits32
0x1c30c  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x1c311  add
0x1c312  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits32
0x1c317  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x1c31c  add
0x1c31d  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x1c322  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x1c327  ldarg.0
0x1c328  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.PlatformPiece::pictureIcon
0x1c32d  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x1c332  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x1c337  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x1c33c  ldc.i4.0
0x1c33d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x1c342  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x1c347  ldarg.0
0x1c348  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.PlatformPiece::pictureIcon
0x1c34d  ldc.i4.2
0x1c34e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_SizeMode(valuetype [System.Windows.Forms]System.Windows.Forms.PictureBoxSizeMode)
0x1c353  ldloc.0
0x1c354  ldarg.0
0x1c355  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.PlatformPiece::btnOk
0x1c35a  ldstr    aBtnok// "btnOk"
0x1c35f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1c364  ldarg.0
0x1c365  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.PlatformPiece::overarchingTableLayoutPanel
0x1c36a  ldarg.0
0x1c36b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.PlatformPiece::btnOk
0x1c370  ldc.i4.2
0x1c371  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x1c376  ldarg.0
0x1c377  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.PlatformPiece::btnOk
0x1c37c  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumButtonSizeWidth
0x1c381  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumButtonSizeHeight
0x1c386  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x1c38b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x1c390  ldarg.0
0x1c391  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.PlatformPiece::btnOk
0x1c396  ldstr    aBtnok// "btnOk"
0x1c39b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1c3a0  ldarg.0
0x1c3a1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.PlatformPiece::btnOk
0x1c3a6  ldarg.0
0x1c3a7  ldftn    instance void System.Deployment.Application.PlatformPiece::btnOk_Click(object sender, class [mscorlib]System.EventArgs e)
0x1c3ad  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1c3b2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x1c3b7  ldloc.0
0x1c3b8  ldarg.0
0x1c3b9  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.PlatformPiece::linkSupport
0x1c3be  ldstr    aLinksupport// "linkSupport"
0x1c3c3  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1c3c8  ldarg.0
0x1c3c9  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.PlatformPiece::linkSupport
0x1c3ce  ldstr    aLinksupport// "linkSupport"
0x1c3d3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1c3d8  ldarg.0
0x1c3d9  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.PlatformPiece::linkSupport
0x1c3de  ldc.i4.1
0x1c3df  callvirt instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::set_TabStop(bool)
0x1c3e4  ldarg.0
0x1c3e5  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.PlatformPiece::linkSupport
0x1c3ea  ldarg.0
0x1c3eb  ldftn    instance void System.Deployment.Application.PlatformPiece::linkSupport_LinkClicked(object sender, class [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventArgs e)
0x1c3f1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventHandler::.ctor(object, native int)
0x1c3f6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::add_LinkClicked(class [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventHandler)
0x1c3fb  ldloc.0
0x1c3fc  ldarg.0
0x1c3fd  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.PlatformPiece::overarchingTableLayoutPanel
0x1c402  ldstr    aOverarchingtab// "overarchingTableLayoutPanel"
0x1c407  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1c40c  ldarg.0
0x1c40d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.PlatformPiece::overarchingTableLayoutPanel
0x1c412  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x1c417  ldarg.0
0x1c418  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.PlatformPiece::pictureIcon
0x1c41d  ldc.i4.0
0x1c41e  ldc.i4.0
0x1c41f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x1c424  ldarg.0
0x1c425  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.PlatformPiece::overarchingTableLayoutPanel
0x1c42a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x1c42f  ldarg.0
0x1c430  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.PlatformPiece::btnOk
0x1c435  ldc.i4.0
0x1c436  ldc.i4.2
0x1c437  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x1c43c  ldarg.0
0x1c43d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.PlatformPiece::overarchingTableLayoutPanel
0x1c442  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x1c447  ldarg.0
0x1c448  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.PlatformPiece::linkSupport
0x1c44d  ldc.i4.1
0x1c44e  ldc.i4.1
0x1c44f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x1c454  ldarg.0
0x1c455  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.PlatformPiece::overarchingTableLayoutPanel
0x1c45a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x1c45f  ldarg.0
0x1c460  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.PlatformPiece::lblMessage
0x1c465  ldc.i4.1
0x1c466  ldc.i4.0
0x1c467  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x1c46c  ldarg.0
0x1c46d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.PlatformPiece::overarchingTableLayoutPanel
0x1c472  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits349
0x1c477  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits88
0x1c47c  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x1c481  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x1c486  ldarg.0
0x1c487  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.PlatformPiece::overarchingTableLayoutPanel
0x1c48c  ldstr    aOverarchingtab// "overarchingTableLayoutPanel"
0x1c491  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1c496  ldloc.0
0x1c497  ldarg.0
0x1c498  ldstr    aThis// "$this"
0x1c49d  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1c4a2  ldarg.0
0x1c4a3  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x1c4a8  ldarg.0
0x1c4a9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.PlatformPiece::overarchingTableLayoutPanel
0x1c4ae  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x1c4b3  ldarg.0
0x1c4b4  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits373
0x1c4b9  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits112
0x1c4be  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x1c4c3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x1c4c8  ldarg.0
0x1c4c9  ldstr    aPlatformpiece// "PlatformPiece"
0x1c4ce  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1c4d3  ldarg.0
0x1c4d4  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.PlatformPiece::pictureIcon
0x1c4d9  callvirt instance void [System]System.ComponentModel.ISupportInitialize::EndInit()
0x1c4de  ldarg.0
0x1c4df  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.PlatformPiece::overarchingTableLayoutPanel
0x1c4e4  ldc.i4.0
0x1c4e5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x1c4ea  ldarg.0
0x1c4eb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.PlatformPiece::overarchingTableLayoutPanel
0x1c4f0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x1c4f5  ldarg.0
0x1c4f6  ldc.i4.0
0x1c4f7  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x1c4fc  ldarg.0
0x1c4fd  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x1c502  ret
```
