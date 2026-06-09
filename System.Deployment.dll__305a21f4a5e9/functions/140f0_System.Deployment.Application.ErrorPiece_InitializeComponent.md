# System.Deployment.Application.ErrorPiece::InitializeComponent

- ea: `0x140f0`
- end: `0x144e9`
- name: `System.Deployment.Application.ErrorPiece::InitializeComponent`
- size: `1017`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14040`

## string_xrefs

- `0x1442f`: `errorLink`
- `0x14459`: `errorLink`

## pseudocode

```c

```

## disassembly

```asm
0x140f0  ldtoken  System.Deployment.Application.ErrorPiece
0x140f5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x140fa  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x140ff  stloc.0
0x14100  ldarg.0
0x14101  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x14106  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ErrorPiece::lblMessage
0x1410b  ldarg.0
0x1410c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0x14111  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ErrorPiece::pictureIcon
0x14116  ldarg.0
0x14117  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x1411c  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.ErrorPiece::btnOk
0x14121  ldarg.0
0x14122  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x14127  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.ErrorPiece::btnSupport
0x1412c  ldarg.0
0x1412d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x14132  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::okDetailsTableLayoutPanel
0x14137  ldarg.0
0x14138  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x1413d  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::overarchingTableLayoutPanel
0x14142  ldarg.0
0x14143  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::.ctor()
0x14148  stfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.ErrorPiece::errorLink
0x1414d  ldarg.0
0x1414e  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ErrorPiece::pictureIcon
0x14153  callvirt instance void [System]System.ComponentModel.ISupportInitialize::BeginInit()
0x14158  ldarg.0
0x14159  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::okDetailsTableLayoutPanel
0x1415e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x14163  ldarg.0
0x14164  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::overarchingTableLayoutPanel
0x14169  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x1416e  ldarg.0
0x1416f  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x14174  ldloc.0
0x14175  ldarg.0
0x14176  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ErrorPiece::lblMessage
0x1417b  ldstr    aLblmessage// "lblMessage"
0x14180  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x14185  ldarg.0
0x14186  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ErrorPiece::lblMessage
0x1418b  ldstr    aLblmessage// "lblMessage"
0x14190  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x14195  ldarg.0
0x14196  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ErrorPiece::lblMessage
0x1419b  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits32
0x141a0  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits6
0x141a5  add
0x141a6  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x141ab  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x141b0  ldc.i4.0
0x141b1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x141b6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x141bb  ldloc.0
0x141bc  ldarg.0
0x141bd  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ErrorPiece::pictureIcon
0x141c2  ldstr    aPictureicon// "pictureIcon"
0x141c7  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x141cc  ldarg.0
0x141cd  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ErrorPiece::pictureIcon
0x141d2  ldstr    aPictureicon// "pictureIcon"
0x141d7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x141dc  ldarg.0
0x141dd  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ErrorPiece::pictureIcon
0x141e2  ldc.i4.0
0x141e3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_TabStop(bool)
0x141e8  ldarg.0
0x141e9  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ErrorPiece::pictureIcon
0x141ee  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits32
0x141f3  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x141f8  add
0x141f9  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits32
0x141fe  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x14203  add
0x14204  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x14209  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x1420e  ldarg.0
0x1420f  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ErrorPiece::pictureIcon
0x14214  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x14219  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x1421e  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x14223  ldc.i4.0
0x14224  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x14229  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x1422e  ldarg.0
0x1422f  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ErrorPiece::pictureIcon
0x14234  ldc.i4.2
0x14235  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_SizeMode(valuetype [System.Windows.Forms]System.Windows.Forms.PictureBoxSizeMode)
0x1423a  ldloc.0
0x1423b  ldarg.0
0x1423c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.ErrorPiece::btnOk
0x14241  ldstr    aBtnok// "btnOk"
0x14246  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1424b  ldarg.0
0x1424c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.ErrorPiece::btnOk
0x14251  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits78
0x14256  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits28
0x1425b  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x14260  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x14265  ldarg.0
0x14266  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.ErrorPiece::btnOk
0x1426b  ldstr    aBtnok// "btnOk"
0x14270  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x14275  ldarg.0
0x14276  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.ErrorPiece::btnOk
0x1427b  ldarg.0
0x1427c  ldftn    instance void System.Deployment.Application.ErrorPiece::btnOk_Click(object sender, class [mscorlib]System.EventArgs e)
0x14282  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x14287  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x1428c  ldarg.0
0x1428d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.ErrorPiece::btnOk
0x14292  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits10
0x14297  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x1429c  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x142a1  ldc.i4.0
0x142a2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x142a7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x142ac  ldloc.0
0x142ad  ldarg.0
0x142ae  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.ErrorPiece::btnSupport
0x142b3  ldstr    aBtnsupport// "btnSupport"
0x142b8  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x142bd  ldarg.0
0x142be  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.ErrorPiece::btnSupport
0x142c3  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits78
0x142c8  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits28
0x142cd  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x142d2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x142d7  ldarg.0
0x142d8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.ErrorPiece::btnSupport
0x142dd  ldstr    aBtnsupport// "btnSupport"
0x142e2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x142e7  ldarg.0
0x142e8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.ErrorPiece::btnSupport
0x142ed  ldarg.0
0x142ee  ldftn    instance void System.Deployment.Application.ErrorPiece::btnSupport_Click(object sender, class [mscorlib]System.EventArgs e)
0x142f4  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x142f9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x142fe  ldarg.0
0x142ff  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.ErrorPiece::btnSupport
0x14304  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits10
0x14309  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x1430e  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledPaddingUnits3
0x14313  ldc.i4.0
0x14314  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x14319  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x1431e  ldloc.0
0x1431f  ldarg.0
0x14320  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::okDetailsTableLayoutPanel
0x14325  ldstr    aOkdetailstable// "okDetailsTableLayoutPanel"
0x1432a  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1432f  ldarg.0
0x14330  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::overarchingTableLayoutPanel
0x14335  ldarg.0
0x14336  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::okDetailsTableLayoutPanel
0x1433b  ldc.i4.2
0x1433c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x14341  ldarg.0
0x14342  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::okDetailsTableLayoutPanel
0x14347  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x1434c  ldarg.0
0x1434d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.ErrorPiece::btnOk
0x14352  ldc.i4.0
0x14353  ldc.i4.0
0x14354  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x14359  ldarg.0
0x1435a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::okDetailsTableLayoutPanel
0x1435f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x14364  ldarg.0
0x14365  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Deployment.Application.ErrorPiece::btnSupport
0x1436a  ldc.i4.1
0x1436b  ldc.i4.0
0x1436c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x14371  ldarg.0
0x14372  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::okDetailsTableLayoutPanel
0x14377  ldstr    aOkdetailstable// "okDetailsTableLayoutPanel"
0x1437c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x14381  ldloc.0
0x14382  ldarg.0
0x14383  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::overarchingTableLayoutPanel
0x14388  ldstr    aOverarchingtab// "overarchingTableLayoutPanel"
0x1438d  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x14392  ldarg.0
0x14393  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::overarchingTableLayoutPanel
0x14398  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x1439d  ldarg.0
0x1439e  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ErrorPiece::pictureIcon
0x143a3  ldc.i4.0
0x143a4  ldc.i4.0
0x143a5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x143aa  ldarg.0
0x143ab  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::overarchingTableLayoutPanel
0x143b0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x143b5  ldarg.0
0x143b6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Deployment.Application.ErrorPiece::lblMessage
0x143bb  ldc.i4.1
0x143bc  ldc.i4.0
0x143bd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x143c2  ldarg.0
0x143c3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::overarchingTableLayoutPanel
0x143c8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x143cd  ldarg.0
0x143ce  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.ErrorPiece::errorLink
0x143d3  ldc.i4.1
0x143d4  ldc.i4.1
0x143d5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x143da  ldarg.0
0x143db  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::overarchingTableLayoutPanel
0x143e0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x143e5  ldarg.0
0x143e6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::okDetailsTableLayoutPanel
0x143eb  ldc.i4.0
0x143ec  ldc.i4.2
0x143ed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x143f2  ldarg.0
0x143f3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::overarchingTableLayoutPanel
0x143f8  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits466
0x143fd  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits32
0x14402  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x14407  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x1440c  ldarg.0
0x1440d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::overarchingTableLayoutPanel
0x14412  ldstr    aOverarchingtab// "overarchingTableLayoutPanel"
0x14417  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1441c  ldarg.0
0x1441d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::overarchingTableLayoutPanel
0x14422  ldc.i4.5
0x14423  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x14428  ldloc.0
0x14429  ldarg.0
0x1442a  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.ErrorPiece::errorLink
0x1442f  ldstr    aErrorlink// "errorLink"
0x14434  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x14439  ldarg.0
0x1443a  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.ErrorPiece::errorLink
0x1443f  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits280
0x14444  ldsfld   int32 System.Deployment.Application.ClickOnceConstants::DpiScaledMinimumSizeUnits32
0x14449  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x1444e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x14453  ldarg.0
0x14454  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.ErrorPiece::errorLink
0x14459  ldstr    aErrorlink// "errorLink"
0x1445e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x14463  ldarg.0
0x14464  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Deployment.Application.ErrorPiece::errorLink
0x14469  ldarg.0
0x1446a  ldftn    instance void System.Deployment.Application.ErrorPiece::errorLink_LinkClicked(object sender, class [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventArgs e)
0x14470  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventHandler::.ctor(object, native int)
0x14475  callvirt instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::add_LinkClicked(class [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventHandler)
0x1447a  ldloc.0
0x1447b  ldarg.0
0x1447c  ldstr    aThis// "$this"
0x14481  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x14486  ldarg.0
0x14487  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x1448c  ldarg.0
0x1448d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::overarchingTableLayoutPanel
0x14492  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x14497  ldarg.0
0x14498  ldstr    aErrorpiece// "ErrorPiece"
0x1449d  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x144a2  ldarg.0
0x144a3  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox System.Deployment.Application.ErrorPiece::pictureIcon
0x144a8  callvirt instance void [System]System.ComponentModel.ISupportInitialize::EndInit()
0x144ad  ldarg.0
0x144ae  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::okDetailsTableLayoutPanel
0x144b3  ldc.i4.0
0x144b4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x144b9  ldarg.0
0x144ba  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::okDetailsTableLayoutPanel
0x144bf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x144c4  ldarg.0
0x144c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::overarchingTableLayoutPanel
0x144ca  ldc.i4.0
0x144cb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x144d0  ldarg.0
0x144d1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Deployment.Application.ErrorPiece::overarchingTableLayoutPanel
0x144d6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x144db  ldarg.0
0x144dc  ldc.i4.0
0x144dd  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x144e2  ldarg.0
0x144e3  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x144e8  ret
```
