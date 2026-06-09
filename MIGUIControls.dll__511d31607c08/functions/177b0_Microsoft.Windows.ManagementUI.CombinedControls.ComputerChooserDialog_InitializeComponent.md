# Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::InitializeComponent

- ea: `0x177b0`
- end: `0x17a5f`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::InitializeComponent`
- size: `687`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x17650`

## callees

- `0x17b30`

## string_xrefs

- `0x17824`: `controlComputerChooser`
- `0x1785d`: `controlComputerChooser`
- `0x17a0a`: `ComputerChooserDialog`

## pseudocode

```c

```

## disassembly

```asm
0x177b0  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog
0x177b5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x177ba  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x177bf  ldarg.0
0x177c0  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser::.ctor()
0x177c5  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::controlComputerChooser
0x177ca  ldarg.0
0x177cb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x177d0  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonOK
0x177d5  ldarg.0
0x177d6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x177db  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonCancel
0x177e0  ldarg.0
0x177e1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x177e6  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::labelSeparator
0x177eb  ldarg.0
0x177ec  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x177f1  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonTableLayoutPanel
0x177f6  ldarg.0
0x177f7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x177fc  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::tableLayoutPanel
0x17801  ldarg.0
0x17802  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::tableLayoutPanel
0x17807  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x1780c  ldarg.0
0x1780d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonTableLayoutPanel
0x17812  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x17817  ldarg.0
0x17818  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x1781d  dup
0x1781e  ldarg.0
0x1781f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::controlComputerChooser
0x17824  ldstr    aControlcompute// "controlComputerChooser"
0x17829  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1782e  ldarg.0
0x1782f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::tableLayoutPanel
0x17834  ldarg.0
0x17835  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::controlComputerChooser
0x1783a  ldc.i4.2
0x1783b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x17840  ldarg.0
0x17841  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::controlComputerChooser
0x17846  ldc.i4   0x1F4
0x1784b  ldc.i4.s 0x69
0x1784d  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x17852  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x17857  ldarg.0
0x17858  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::controlComputerChooser
0x1785d  ldstr    aControlcompute// "controlComputerChooser"
0x17862  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x17867  dup
0x17868  ldarg.0
0x17869  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonOK
0x1786e  ldstr    aButtonok// "buttonOK"
0x17873  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x17878  ldarg.0
0x17879  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonOK
0x1787e  ldc.i4.1
0x1787f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x17884  ldarg.0
0x17885  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonOK
0x1788a  ldstr    aButtonok// "buttonOK"
0x1788f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x17894  ldarg.0
0x17895  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonOK
0x1789a  ldarg.0
0x1789b  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonOK_Click(object sender, class [mscorlib]System.EventArgs e)
0x178a1  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x178a6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x178ab  dup
0x178ac  ldarg.0
0x178ad  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonCancel
0x178b2  ldstr    aButtoncancel// "buttonCancel"
0x178b7  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x178bc  ldarg.0
0x178bd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonCancel
0x178c2  ldc.i4.2
0x178c3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x178c8  ldarg.0
0x178c9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonCancel
0x178ce  ldstr    aButtoncancel// "buttonCancel"
0x178d3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x178d8  dup
0x178d9  ldarg.0
0x178da  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::labelSeparator
0x178df  ldstr    aLabelseparator// "labelSeparator"
0x178e4  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x178e9  ldarg.0
0x178ea  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::labelSeparator
0x178ef  ldc.i4.2
0x178f0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_BorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.BorderStyle)
0x178f5  ldarg.0
0x178f6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::tableLayoutPanel
0x178fb  ldarg.0
0x178fc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::labelSeparator
0x17901  ldc.i4.2
0x17902  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x17907  ldarg.0
0x17908  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::labelSeparator
0x1790d  ldstr    aLabelseparator// "labelSeparator"
0x17912  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x17917  dup
0x17918  ldarg.0
0x17919  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonTableLayoutPanel
0x1791e  ldstr    aButtontablelay// "buttonTableLayoutPanel"
0x17923  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x17928  ldarg.0
0x17929  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonTableLayoutPanel
0x1792e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x17933  ldarg.0
0x17934  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonOK
0x17939  ldc.i4.0
0x1793a  ldc.i4.0
0x1793b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x17940  ldarg.0
0x17941  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonTableLayoutPanel
0x17946  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x1794b  ldarg.0
0x1794c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonCancel
0x17951  ldc.i4.1
0x17952  ldc.i4.0
0x17953  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x17958  ldarg.0
0x17959  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonTableLayoutPanel
0x1795e  ldstr    aButtontablelay// "buttonTableLayoutPanel"
0x17963  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x17968  dup
0x17969  ldarg.0
0x1796a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::tableLayoutPanel
0x1796f  ldstr    aTablelayoutpan_0// "tableLayoutPanel"
0x17974  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x17979  ldarg.0
0x1797a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::tableLayoutPanel
0x1797f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x17984  ldarg.0
0x17985  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonTableLayoutPanel
0x1798a  ldc.i4.1
0x1798b  ldc.i4.2
0x1798c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x17991  ldarg.0
0x17992  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::tableLayoutPanel
0x17997  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x1799c  ldarg.0
0x1799d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlComputerChooser Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::controlComputerChooser
0x179a2  ldc.i4.0
0x179a3  ldc.i4.0
0x179a4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x179a9  ldarg.0
0x179aa  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::tableLayoutPanel
0x179af  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x179b4  ldarg.0
0x179b5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::labelSeparator
0x179ba  ldc.i4.0
0x179bb  ldc.i4.1
0x179bc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x179c1  ldarg.0
0x179c2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::tableLayoutPanel
0x179c7  ldstr    aTablelayoutpan_0// "tableLayoutPanel"
0x179cc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x179d1  ldarg.0
0x179d2  ldstr    aThis// "$this"
0x179d7  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x179dc  ldarg.0
0x179dd  ldc.i4.1
0x179de  call     instance void [System.Windows.Forms]System.Windows.Forms.ContainerControl::set_AutoScaleMode(valuetype [System.Windows.Forms]System.Windows.Forms.AutoScaleMode)
0x179e3  ldarg.0
0x179e4  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x179e9  ldarg.0
0x179ea  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::tableLayoutPanel
0x179ef  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x179f4  ldarg.0
0x179f5  ldc.i4.3
0x179f6  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_FormBorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FormBorderStyle)
0x179fb  ldarg.0
0x179fc  ldc.i4.0
0x179fd  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_MaximizeBox(bool)
0x17a02  ldarg.0
0x17a03  ldc.i4.0
0x17a04  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_MinimizeBox(bool)
0x17a09  ldarg.0
0x17a0a  ldstr    aComputerchoose// "ComputerChooserDialog"
0x17a0f  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x17a14  ldarg.0
0x17a15  ldc.i4.0
0x17a16  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_ShowIcon(bool)
0x17a1b  ldarg.0
0x17a1c  ldc.i4.0
0x17a1d  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_ShowInTaskbar(bool)
0x17a22  ldarg.0
0x17a23  ldarg.0
0x17a24  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::ComputerChooserDialog_Load(object sender, class [mscorlib]System.EventArgs e)
0x17a2a  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x17a2f  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::add_Load(class [mscorlib]System.EventHandler)
0x17a34  ldarg.0
0x17a35  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::tableLayoutPanel
0x17a3a  ldc.i4.0
0x17a3b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x17a40  ldarg.0
0x17a41  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonTableLayoutPanel
0x17a46  ldc.i4.0
0x17a47  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x17a4c  ldarg.0
0x17a4d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ComputerChooserDialog::buttonTableLayoutPanel
0x17a52  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x17a57  ldarg.0
0x17a58  ldc.i4.0
0x17a59  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x17a5e  ret
```
