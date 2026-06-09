# Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxHidden_Click

- ea: `0x731e0`
- end: `0x73270`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxHidden_Click`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x12ed0`
- `0x14ed0`
- `0x14ef0`
- `0x14f10`
- `0x14f70`
- `0x14fb0`
- `0x14ff0`
- `0x15010`
- `0x15020`
- `0x15110`
- `0x72cb0`
- `0x72e00`
- `0x731e0`

## string_xrefs

- `0x73216`: `ApplicationTaskScheduler`
- `0x73226`: `TaskHiddenToNonHiddenWarning`

## pseudocode

```c

```

## disassembly

```asm
0x731e0  ldarg.0
0x731e1  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxHidden
0x731e6  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.CheckBox::get_Checked()
0x731eb  brtrue.s loc_73263
0x731ed  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::.ctor()
0x731f2  pop
0x731f3  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::.ctor()
0x731f8  dup
0x731f9  ldc.i4.4
0x731fa  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Buttons(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons value)
0x731ff  dup
0x73200  ldc.i4.s 0x30
0x73202  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon value)
0x73207  dup
0x73208  ldc.i4.0
0x73209  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_DefaultButton(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxDefaultButton value)
0x7320e  dup
0x7320f  ldc.i4.0
0x73210  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Options(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxOptions value)
0x73215  dup
0x73216  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x7321b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x73220  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Caption(string value)
0x73225  dup
0x73226  ldstr    aTaskhiddentono// "TaskHiddenToNonHiddenWarning"
0x7322b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x73230  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_Text(string value)
0x73235  dup
0x73236  ldarg.0
0x73237  call     instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x7323c  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams::set_ParentWindow(class [System.Windows.Forms]System.Windows.Forms.IWin32Window value)
0x73241  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.UIConsole::ShowMessageBox(class Microsoft.Windows.ManagementUI.CombinedControls.MessageBoxParams messageParams)
0x73246  ldc.i4.7
0x73247  bne.un.s loc_73256
0x73249  ldarg.0
0x7324a  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxHidden
0x7324f  ldc.i4.1
0x73250  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::set_Checked(bool)
0x73255  ret
0x73256  ldarg.0
0x73257  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::ControlsToData()
0x7325c  ldarg.0
0x7325d  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::DataToControls()
0x73262  ret
0x73263  ldarg.0
0x73264  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::ControlsToData()
0x73269  ldarg.0
0x7326a  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::DataToControls()
0x7326f  ret
```
