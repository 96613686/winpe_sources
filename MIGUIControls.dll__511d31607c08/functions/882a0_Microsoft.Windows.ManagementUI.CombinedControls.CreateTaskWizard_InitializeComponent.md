# Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::InitializeComponent

- ea: `0x882a0`
- end: `0x889de`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::InitializeComponent`
- size: `1854`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x87950`

## string_xrefs

- `0x88419`: `pictureBoxTasks`
- `0x88429`: `pictureBoxTasks`
- `0x88996`: `CreateTaskWizard`

## pseudocode

```c

```

## disassembly

```asm
0x882a0  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard
0x882a5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x882aa  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x882af  ldarg.0
0x882b0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x882b5  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::wizardDynamicPanel
0x882ba  ldarg.0
0x882bb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0x882c0  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::pictureBoxTasks
0x882c5  ldarg.0
0x882c6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x882cb  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::titleLabel
0x882d0  ldarg.0
0x882d1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x882d6  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::groupBox3
0x882db  ldarg.0
0x882dc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x882e1  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::cancelBtn
0x882e6  ldarg.0
0x882e7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x882ec  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::nextBtn
0x882f1  ldarg.0
0x882f2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x882f7  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::backBtn
0x882fc  ldarg.0
0x882fd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x88302  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::groupBox1
0x88307  ldarg.0
0x88308  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor()
0x8830d  stfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::columnName
0x88312  ldarg.0
0x88313  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x88318  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page1
0x8831d  ldarg.0
0x8831e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x88323  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page2
0x88328  ldarg.0
0x88329  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x8832e  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page3
0x88333  ldarg.0
0x88334  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x88339  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page4
0x8833e  ldarg.0
0x8833f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x88344  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page5
0x88349  ldarg.0
0x8834a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x8834f  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page6
0x88354  ldarg.0
0x88355  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x8835a  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page7
0x8835f  ldarg.0
0x88360  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x88365  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page8
0x8836a  ldarg.0
0x8836b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x88370  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::tableLayoutPanel
0x88375  ldarg.0
0x88376  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x8837b  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::panelWindowBackground1
0x88380  ldarg.0
0x88381  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x88386  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::panelWindowBackground2
0x8838b  ldarg.0
0x8838c  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::pictureBoxTasks
0x88391  callvirt instance void [System]System.ComponentModel.ISupportInitialize::BeginInit()
0x88396  ldarg.0
0x88397  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::tableLayoutPanel
0x8839c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x883a1  ldarg.0
0x883a2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::panelWindowBackground1
0x883a7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x883ac  ldarg.0
0x883ad  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::panelWindowBackground2
0x883b2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x883b7  ldarg.0
0x883b8  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x883bd  dup
0x883be  ldarg.0
0x883bf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::wizardDynamicPanel
0x883c4  ldstr    aWizarddynamicp// "wizardDynamicPanel"
0x883c9  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x883ce  ldarg.0
0x883cf  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::tableLayoutPanel
0x883d4  ldarg.0
0x883d5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::wizardDynamicPanel
0x883da  ldc.i4.3
0x883db  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x883e0  ldarg.0
0x883e1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::wizardDynamicPanel
0x883e6  ldstr    aWizarddynamicp// "wizardDynamicPanel"
0x883eb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x883f0  ldarg.0
0x883f1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::tableLayoutPanel
0x883f6  ldarg.0
0x883f7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::wizardDynamicPanel
0x883fc  ldc.i4.8
0x883fd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetRowSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x88402  ldarg.0
0x88403  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::pictureBoxTasks
0x88408  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::get_Transparent()
0x8840d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x88412  dup
0x88413  ldarg.0
0x88414  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::pictureBoxTasks
0x88419  ldstr    aPictureboxtask// "pictureBoxTasks"
0x8841e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x88423  ldarg.0
0x88424  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::pictureBoxTasks
0x88429  ldstr    aPictureboxtask// "pictureBoxTasks"
0x8842e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x88433  ldarg.0
0x88434  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::pictureBoxTasks
0x88439  ldc.i4.0
0x8843a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_TabStop(bool)
0x8843f  dup
0x88440  ldarg.0
0x88441  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::titleLabel
0x88446  ldstr    aTitlelabel// "titleLabel"
0x8844b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x88450  ldarg.0
0x88451  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::titleLabel
0x88456  ldstr    aTitlelabel// "titleLabel"
0x8845b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x88460  dup
0x88461  ldarg.0
0x88462  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::groupBox3
0x88467  ldstr    aGroupbox3// "groupBox3"
0x8846c  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x88471  ldarg.0
0x88472  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::groupBox3
0x88477  ldstr    aGroupbox3// "groupBox3"
0x8847c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x88481  ldarg.0
0x88482  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::groupBox3
0x88487  ldc.i4.0
0x88488  callvirt instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::set_TabStop(bool)
0x8848d  dup
0x8848e  ldarg.0
0x8848f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::cancelBtn
0x88494  ldstr    aCancelbtn_0// "cancelBtn"
0x88499  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8849e  ldarg.0
0x8849f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::cancelBtn
0x884a4  ldc.i4.2
0x884a5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x884aa  ldarg.0
0x884ab  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::cancelBtn
0x884b0  ldstr    aCancelbtn_0// "cancelBtn"
0x884b5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x884ba  ldarg.0
0x884bb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::cancelBtn
0x884c0  ldarg.0
0x884c1  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::cancelBtn_Click(object sender, class [mscorlib]System.EventArgs e)
0x884c7  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x884cc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x884d1  dup
0x884d2  ldarg.0
0x884d3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::nextBtn
0x884d8  ldstr    aNextbtn// "nextBtn"
0x884dd  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x884e2  ldarg.0
0x884e3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::nextBtn
0x884e8  ldstr    aNextbtn// "nextBtn"
0x884ed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x884f2  ldarg.0
0x884f3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::nextBtn
0x884f8  ldarg.0
0x884f9  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::nextBtn_Click(object sender, class [mscorlib]System.EventArgs e)
0x884ff  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x88504  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x88509  dup
0x8850a  ldarg.0
0x8850b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::backBtn
0x88510  ldstr    aBackbtn// "backBtn"
0x88515  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8851a  ldarg.0
0x8851b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::backBtn
0x88520  ldstr    aBackbtn// "backBtn"
0x88525  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8852a  ldarg.0
0x8852b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::backBtn
0x88530  ldarg.0
0x88531  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::backBtn_Click(object sender, class [mscorlib]System.EventArgs e)
0x88537  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8853c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x88541  dup
0x88542  ldarg.0
0x88543  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::groupBox1
0x88548  ldstr    aGroupbox1// "groupBox1"
0x8854d  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x88552  ldarg.0
0x88553  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::groupBox1
0x88558  ldstr    aGroupbox1// "groupBox1"
0x8855d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x88562  ldarg.0
0x88563  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::groupBox1
0x88568  ldc.i4.0
0x88569  callvirt instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::set_TabStop(bool)
0x8856e  ldarg.0
0x8856f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::columnName
0x88574  ldstr    aColumnname// "columnName"
0x88579  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::set_Name(string)
0x8857e  dup
0x8857f  ldarg.0
0x88580  ldfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::columnName
0x88585  ldstr    aColumnname// "columnName"
0x8858a  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8858f  ldarg.0
0x88590  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::tableLayoutPanel
0x88595  ldarg.0
0x88596  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page1
0x8859b  ldc.i4.2
0x8859c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x885a1  dup
0x885a2  ldarg.0
0x885a3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page1
0x885a8  ldstr    aPage1// "page1"
0x885ad  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x885b2  ldarg.0
0x885b3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page1
0x885b8  ldstr    aPage1// "page1"
0x885bd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x885c2  ldarg.0
0x885c3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::tableLayoutPanel
0x885c8  ldarg.0
0x885c9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page2
0x885ce  ldc.i4.2
0x885cf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x885d4  dup
0x885d5  ldarg.0
0x885d6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page2
0x885db  ldstr    aPage2// "page2"
0x885e0  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x885e5  ldarg.0
0x885e6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page2
0x885eb  ldstr    aPage2// "page2"
0x885f0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x885f5  ldarg.0
0x885f6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::tableLayoutPanel
0x885fb  ldarg.0
0x885fc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page3
0x88601  ldc.i4.2
0x88602  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x88607  dup
0x88608  ldarg.0
0x88609  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page3
0x8860e  ldstr    aPage3// "page3"
0x88613  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x88618  ldarg.0
0x88619  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page3
0x8861e  ldstr    aPage3// "page3"
0x88623  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x88628  ldarg.0
0x88629  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::tableLayoutPanel
0x8862e  ldarg.0
0x8862f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page4
0x88634  ldc.i4.2
0x88635  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x8863a  dup
0x8863b  ldarg.0
0x8863c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page4
0x88641  ldstr    aPage4// "page4"
0x88646  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8864b  ldarg.0
0x8864c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page4
0x88651  ldstr    aPage4// "page4"
0x88656  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8865b  ldarg.0
0x8865c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::tableLayoutPanel
0x88661  ldarg.0
0x88662  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page5
0x88667  ldc.i4.2
0x88668  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x8866d  dup
0x8866e  ldarg.0
0x8866f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page5
0x88674  ldstr    aPage5// "page5"
0x88679  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8867e  ldarg.0
0x8867f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page5
0x88684  ldstr    aPage5// "page5"
0x88689  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8868e  ldarg.0
0x8868f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::tableLayoutPanel
0x88694  ldarg.0
0x88695  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page6
0x8869a  ldc.i4.2
0x8869b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x886a0  dup
0x886a1  ldarg.0
0x886a2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page6
0x886a7  ldstr    aPage6// "page6"
0x886ac  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x886b1  ldarg.0
0x886b2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::page6
0x886b7  ldstr    aPage6// "page6"
0x886bc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x886c1  ldarg.0
0x886c2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.CreateTaskWizard::tableLayoutPanel
  ... truncated ...
```
