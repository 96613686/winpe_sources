# Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::InitializeComponent

- ea: `0x25830`
- end: `0x25b8b`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::InitializeComponent`
- size: `859`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x25130`

## callees

- `0x227d0`

## string_xrefs

- `0x25953`: `buttonCopy`
- `0x25963`: `buttonCopy`

## pseudocode

```c

```

## disassembly

```asm
0x25830  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog
0x25835  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2583a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x2583f  ldarg.0
0x25840  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x25845  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::tableBottom
0x2584a  ldarg.0
0x2584b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x25850  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::buttonCopy
0x25855  ldarg.0
0x25856  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::.ctor()
0x2585b  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::eventProperties1
0x25860  ldarg.0
0x25861  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x25866  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::closeButton
0x2586b  ldarg.0
0x2586c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x25871  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::btnNext
0x25876  ldarg.0
0x25877  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x2587c  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::btnPrevious
0x25881  ldarg.0
0x25882  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x25887  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::panel2
0x2588c  ldarg.0
0x2588d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x25892  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::panel1
0x25897  ldarg.0
0x25898  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::tableBottom
0x2589d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x258a2  ldarg.0
0x258a3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::panel1
0x258a8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x258ad  ldarg.0
0x258ae  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x258b3  dup
0x258b4  ldarg.0
0x258b5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::tableBottom
0x258ba  ldstr    aTablebottom// "tableBottom"
0x258bf  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x258c4  ldarg.0
0x258c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::tableBottom
0x258ca  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x258cf  ldarg.0
0x258d0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::buttonCopy
0x258d5  ldc.i4.0
0x258d6  ldc.i4.2
0x258d7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x258dc  ldarg.0
0x258dd  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::tableBottom
0x258e2  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x258e7  ldarg.0
0x258e8  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::eventProperties1
0x258ed  ldc.i4.0
0x258ee  ldc.i4.0
0x258ef  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x258f4  ldarg.0
0x258f5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::tableBottom
0x258fa  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x258ff  ldarg.0
0x25900  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::closeButton
0x25905  ldc.i4.1
0x25906  ldc.i4.2
0x25907  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x2590c  ldarg.0
0x2590d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::tableBottom
0x25912  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x25917  ldarg.0
0x25918  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::btnNext
0x2591d  ldc.i4.2
0x2591e  ldc.i4.1
0x2591f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x25924  ldarg.0
0x25925  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::tableBottom
0x2592a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x2592f  ldarg.0
0x25930  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::btnPrevious
0x25935  ldc.i4.2
0x25936  ldc.i4.0
0x25937  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x2593c  ldarg.0
0x2593d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::tableBottom
0x25942  ldstr    aTablebottom// "tableBottom"
0x25947  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2594c  dup
0x2594d  ldarg.0
0x2594e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::buttonCopy
0x25953  ldstr    aButtoncopy// "buttonCopy"
0x25958  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x2595d  ldarg.0
0x2595e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::buttonCopy
0x25963  ldstr    aButtoncopy// "buttonCopy"
0x25968  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x2596d  ldarg.0
0x2596e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::buttonCopy
0x25973  ldarg.0
0x25974  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::ButtonCopy_Click(object sender, class [mscorlib]System.EventArgs e)
0x2597a  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x2597f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x25984  ldarg.0
0x25985  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::tableBottom
0x2598a  ldarg.0
0x2598b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::eventProperties1
0x25990  ldc.i4.2
0x25991  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x25996  dup
0x25997  ldarg.0
0x25998  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::eventProperties1
0x2599d  ldstr    aEventpropertie_3// "eventProperties1"
0x259a2  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x259a7  ldarg.0
0x259a8  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::eventProperties1
0x259ad  ldstr    aEventpropertie_3// "eventProperties1"
0x259b2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x259b7  ldarg.0
0x259b8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::tableBottom
0x259bd  ldarg.0
0x259be  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::eventProperties1
0x259c3  ldc.i4.2
0x259c4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetRowSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x259c9  dup
0x259ca  ldarg.0
0x259cb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::closeButton
0x259d0  ldstr    aClosebutton// "closeButton"
0x259d5  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x259da  ldarg.0
0x259db  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::tableBottom
0x259e0  ldarg.0
0x259e1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::closeButton
0x259e6  ldc.i4.2
0x259e7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x259ec  ldarg.0
0x259ed  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::closeButton
0x259f2  ldc.i4.2
0x259f3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x259f8  ldarg.0
0x259f9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::closeButton
0x259fe  ldstr    aClosebutton// "closeButton"
0x25a03  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x25a08  ldarg.0
0x25a09  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::closeButton
0x25a0e  ldarg.0
0x25a0f  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::OkButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x25a15  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x25a1a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x25a1f  dup
0x25a20  ldarg.0
0x25a21  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::btnNext
0x25a26  ldstr    aBtnnext// "btnNext"
0x25a2b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x25a30  ldarg.0
0x25a31  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::btnNext
0x25a36  ldstr    aBtnnext// "btnNext"
0x25a3b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x25a40  ldarg.0
0x25a41  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::btnNext
0x25a46  ldc.i4.1
0x25a47  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x25a4c  ldarg.0
0x25a4d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::btnNext
0x25a52  ldarg.0
0x25a53  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::btnNext_Click(object sender, class [mscorlib]System.EventArgs e)
0x25a59  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x25a5e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x25a63  dup
0x25a64  ldarg.0
0x25a65  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::btnPrevious
0x25a6a  ldstr    aBtnprevious// "btnPrevious"
0x25a6f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x25a74  ldarg.0
0x25a75  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::btnPrevious
0x25a7a  ldstr    aBtnprevious// "btnPrevious"
0x25a7f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x25a84  ldarg.0
0x25a85  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::btnPrevious
0x25a8a  ldc.i4.1
0x25a8b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x25a90  ldarg.0
0x25a91  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::btnPrevious
0x25a96  ldarg.0
0x25a97  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::btnPrevious_Click(object sender, class [mscorlib]System.EventArgs e)
0x25a9d  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x25aa2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x25aa7  dup
0x25aa8  ldarg.0
0x25aa9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::panel2
0x25aae  ldstr    aPanel2// "panel2"
0x25ab3  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x25ab8  ldarg.0
0x25ab9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::panel2
0x25abe  ldstr    aPanel2// "panel2"
0x25ac3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x25ac8  ldarg.0
0x25ac9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::panel1
0x25ace  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x25ad3  ldarg.0
0x25ad4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::tableBottom
0x25ad9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x25ade  dup
0x25adf  ldarg.0
0x25ae0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::panel1
0x25ae5  ldstr    aPanel1// "panel1"
0x25aea  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x25aef  ldarg.0
0x25af0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::panel1
0x25af5  ldstr    aPanel1// "panel1"
0x25afa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x25aff  ldarg.0
0x25b00  ldstr    aThis// "$this"
0x25b05  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x25b0a  ldarg.0
0x25b0b  ldarg.0
0x25b0c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::closeButton
0x25b11  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_CancelButton(class [System.Windows.Forms]System.Windows.Forms.IButtonControl)
0x25b16  ldarg.0
0x25b17  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x25b1c  ldarg.0
0x25b1d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::panel1
0x25b22  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x25b27  ldarg.0
0x25b28  ldc.i4.0
0x25b29  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_MaximizeBox(bool)
0x25b2e  ldarg.0
0x25b2f  ldc.i4.0
0x25b30  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_MinimizeBox(bool)
0x25b35  ldarg.0
0x25b36  ldstr    aEventpropertie_4// "EventPropertiesDialog"
0x25b3b  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x25b40  ldarg.0
0x25b41  ldc.i4.1
0x25b42  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_ShowInTaskbar(bool)
0x25b47  ldarg.0
0x25b48  ldarg.0
0x25b49  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::EventPropertiesDialog_Resize(object sender, class [mscorlib]System.EventArgs e)
0x25b4f  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x25b54  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Resize(class [mscorlib]System.EventHandler)
0x25b59  ldarg.0
0x25b5a  ldarg.0
0x25b5b  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::EventPropertiesDialog_Load(object sender, class [mscorlib]System.EventArgs e)
0x25b61  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x25b66  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::add_Load(class [mscorlib]System.EventHandler)
0x25b6b  ldarg.0
0x25b6c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::tableBottom
0x25b71  ldc.i4.0
0x25b72  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x25b77  ldarg.0
0x25b78  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesDialog::panel1
0x25b7d  ldc.i4.0
0x25b7e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x25b83  ldarg.0
0x25b84  ldc.i4.0
0x25b85  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x25b8a  ret
```
