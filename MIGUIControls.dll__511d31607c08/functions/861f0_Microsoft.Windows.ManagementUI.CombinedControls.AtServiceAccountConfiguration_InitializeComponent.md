# Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::InitializeComponent

- ea: `0x861f0`
- end: `0x86578`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::InitializeComponent`
- size: `904`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x85d30`

## string_xrefs

- `0x8630f`: `tableLayoutPanelATService`
- `0x86397`: `tableLayoutPanelATService`
- `0x8652b`: `AtServiceAccountConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x861f0  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration
0x861f5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x861fa  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x861ff  ldarg.0
0x86200  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x86205  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::systemAccountRadioButton
0x8620a  ldarg.0
0x8620b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x86210  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::thisAccountRadioButton
0x86215  ldarg.0
0x86216  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x8621b  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelATService
0x86220  ldarg.0
0x86221  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x86226  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::labelDescription
0x8622b  ldarg.0
0x8622c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x86231  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelDialog
0x86236  ldarg.0
0x86237  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x8623c  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::okButton
0x86241  ldarg.0
0x86242  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x86247  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::cancelButton
0x8624c  ldarg.0
0x8624d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x86252  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::buttonBrowse
0x86257  ldarg.0
0x86258  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelATService
0x8625d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x86262  ldarg.0
0x86263  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelDialog
0x86268  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x8626d  ldarg.0
0x8626e  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x86273  dup
0x86274  ldarg.0
0x86275  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::systemAccountRadioButton
0x8627a  ldstr    aSystemaccountr// "systemAccountRadioButton"
0x8627f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x86284  ldarg.0
0x86285  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::systemAccountRadioButton
0x8628a  ldc.i4.1
0x8628b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_Checked(bool)
0x86290  ldarg.0
0x86291  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelATService
0x86296  ldarg.0
0x86297  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::systemAccountRadioButton
0x8629c  ldc.i4.3
0x8629d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x862a2  ldarg.0
0x862a3  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::systemAccountRadioButton
0x862a8  ldstr    aSystemaccountr// "systemAccountRadioButton"
0x862ad  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x862b2  ldarg.0
0x862b3  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::systemAccountRadioButton
0x862b8  ldc.i4.1
0x862b9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_TabStop(bool)
0x862be  ldarg.0
0x862bf  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::systemAccountRadioButton
0x862c4  ldarg.0
0x862c5  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::RadioButton_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x862cb  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x862d0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x862d5  dup
0x862d6  ldarg.0
0x862d7  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::thisAccountRadioButton
0x862dc  ldstr    aThisaccountrad// "thisAccountRadioButton"
0x862e1  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x862e6  ldarg.0
0x862e7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelATService
0x862ec  ldarg.0
0x862ed  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::thisAccountRadioButton
0x862f2  ldc.i4.2
0x862f3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x862f8  ldarg.0
0x862f9  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::thisAccountRadioButton
0x862fe  ldstr    aThisaccountrad// "thisAccountRadioButton"
0x86303  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x86308  dup
0x86309  ldarg.0
0x8630a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelATService
0x8630f  ldstr    aTablelayoutpan_23// "tableLayoutPanelATService"
0x86314  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x86319  ldarg.0
0x8631a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelATService
0x8631f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x86324  ldarg.0
0x86325  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::systemAccountRadioButton
0x8632a  ldc.i4.0
0x8632b  ldc.i4.1
0x8632c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x86331  ldarg.0
0x86332  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelATService
0x86337  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8633c  ldarg.0
0x8633d  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::thisAccountRadioButton
0x86342  ldc.i4.0
0x86343  ldc.i4.2
0x86344  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x86349  ldarg.0
0x8634a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelATService
0x8634f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x86354  ldarg.0
0x86355  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::labelDescription
0x8635a  ldc.i4.0
0x8635b  ldc.i4.0
0x8635c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x86361  ldarg.0
0x86362  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelATService
0x86367  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8636c  ldarg.0
0x8636d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelDialog
0x86372  ldc.i4.1
0x86373  ldc.i4.3
0x86374  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x86379  ldarg.0
0x8637a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelATService
0x8637f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x86384  ldarg.0
0x86385  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::buttonBrowse
0x8638a  ldc.i4.2
0x8638b  ldc.i4.2
0x8638c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x86391  ldarg.0
0x86392  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelATService
0x86397  ldstr    aTablelayoutpan_23// "tableLayoutPanelATService"
0x8639c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x863a1  dup
0x863a2  ldarg.0
0x863a3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::labelDescription
0x863a8  ldstr    aLabeldescripti// "labelDescription"
0x863ad  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x863b2  ldarg.0
0x863b3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelATService
0x863b8  ldarg.0
0x863b9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::labelDescription
0x863be  ldc.i4.3
0x863bf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x863c4  ldarg.0
0x863c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::labelDescription
0x863ca  ldstr    aLabeldescripti// "labelDescription"
0x863cf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x863d4  dup
0x863d5  ldarg.0
0x863d6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelDialog
0x863db  ldstr    aTablelayoutpan_24// "tableLayoutPanelDialog"
0x863e0  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x863e5  ldarg.0
0x863e6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelATService
0x863eb  ldarg.0
0x863ec  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelDialog
0x863f1  ldc.i4.2
0x863f2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x863f7  ldarg.0
0x863f8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelDialog
0x863fd  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x86402  ldarg.0
0x86403  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::okButton
0x86408  ldc.i4.0
0x86409  ldc.i4.0
0x8640a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x8640f  ldarg.0
0x86410  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelDialog
0x86415  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8641a  ldarg.0
0x8641b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::cancelButton
0x86420  ldc.i4.1
0x86421  ldc.i4.0
0x86422  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x86427  ldarg.0
0x86428  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelDialog
0x8642d  ldstr    aTablelayoutpan_24// "tableLayoutPanelDialog"
0x86432  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x86437  dup
0x86438  ldarg.0
0x86439  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::okButton
0x8643e  ldstr    aOkbutton// "okButton"
0x86443  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x86448  ldarg.0
0x86449  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::okButton
0x8644e  ldc.i4.s 0x46
0x86450  ldc.i4.0
0x86451  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x86456  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x8645b  ldarg.0
0x8645c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::okButton
0x86461  ldstr    aOkbutton// "okButton"
0x86466  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8646b  ldarg.0
0x8646c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::okButton
0x86471  ldarg.0
0x86472  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::okButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x86478  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8647d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x86482  dup
0x86483  ldarg.0
0x86484  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::cancelButton
0x86489  ldstr    aCancelbutton// "cancelButton"
0x8648e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x86493  ldarg.0
0x86494  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::cancelButton
0x86499  ldstr    aCancelbutton// "cancelButton"
0x8649e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x864a3  ldarg.0
0x864a4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::cancelButton
0x864a9  ldarg.0
0x864aa  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::cancelButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x864b0  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x864b5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x864ba  dup
0x864bb  ldarg.0
0x864bc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::buttonBrowse
0x864c1  ldstr    aButtonbrowse// "buttonBrowse"
0x864c6  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x864cb  ldarg.0
0x864cc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::buttonBrowse
0x864d1  ldstr    aButtonbrowse// "buttonBrowse"
0x864d6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x864db  ldarg.0
0x864dc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::buttonBrowse
0x864e1  ldarg.0
0x864e2  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::buttonBrowse_Click(object sender, class [mscorlib]System.EventArgs e)
0x864e8  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x864ed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x864f2  ldarg.0
0x864f3  ldstr    aThis// "$this"
0x864f8  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x864fd  ldarg.0
0x864fe  ldc.i4.1
0x864ff  call     instance void [System.Windows.Forms]System.Windows.Forms.ContainerControl::set_AutoScaleMode(valuetype [System.Windows.Forms]System.Windows.Forms.AutoScaleMode)
0x86504  ldarg.0
0x86505  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x8650a  ldarg.0
0x8650b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelATService
0x86510  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x86515  ldarg.0
0x86516  ldc.i4.3
0x86517  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_FormBorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FormBorderStyle)
0x8651c  ldarg.0
0x8651d  ldc.i4.0
0x8651e  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_MaximizeBox(bool)
0x86523  ldarg.0
0x86524  ldc.i4.0
0x86525  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_MinimizeBox(bool)
0x8652a  ldarg.0
0x8652b  ldstr    aAtserviceaccou_0// "AtServiceAccountConfiguration"
0x86530  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x86535  ldarg.0
0x86536  ldc.i4.0
0x86537  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_ShowInTaskbar(bool)
0x8653c  ldarg.0
0x8653d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelATService
0x86542  ldc.i4.0
0x86543  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x86548  ldarg.0
0x86549  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelATService
0x8654e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x86553  ldarg.0
0x86554  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelDialog
0x86559  ldc.i4.0
0x8655a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x8655f  ldarg.0
0x86560  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AtServiceAccountConfiguration::tableLayoutPanelDialog
0x86565  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x8656a  ldarg.0
0x8656b  ldc.i4.0
0x8656c  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x86571  ldarg.0
0x86572  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x86577  ret
```
