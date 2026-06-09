# Microsoft.Windows.ManagementUI.CombinedControls.ControlEmailAction::FileBrowser

- ea: `0x6ae60`
- end: `0x6aeb5`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlEmailAction::FileBrowser`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x6aff0`

## callees

- `0x12ed0`
- `0x13670`
- `0x6ae60`

## string_xrefs

- `0x6ae67`: `TaskInitialDirectoryForActionEmailAttachment`
- `0x6ae77`: `TaskFileFiltersForActionEmailAttachment`

## pseudocode

```c

```

## disassembly

```asm
0x6ae60  newobj   instance void [System.Windows.Forms]System.Windows.Forms.OpenFileDialog::.ctor()
0x6ae65  stloc.0
0x6ae66  ldloc.0
0x6ae67  ldstr    aTaskinitialdir_0// "TaskInitialDirectoryForActionEmailAttac"...
0x6ae6c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6ae71  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_InitialDirectory(string)
0x6ae76  ldloc.0
0x6ae77  ldstr    aTaskfilefilter_0// "TaskFileFiltersForActionEmailAttachment"
0x6ae7c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6ae81  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_Filter(string)
0x6ae86  ldloc.0
0x6ae87  ldc.i4.2
0x6ae88  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_FilterIndex(int32)
0x6ae8d  ldloc.0
0x6ae8e  ldc.i4.1
0x6ae8f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_RestoreDirectory(bool)
0x6ae94  ldloc.0
0x6ae95  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [System.Windows.Forms]System.Windows.Forms.CommonDialog::ShowDialog()
0x6ae9a  ldc.i4.1
0x6ae9b  bne.un.s loc_6AEAE
0x6ae9d  ldarg.0
0x6ae9e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlEmailAction::textBoxAttachment
0x6aea3  ldloc.0
0x6aea4  callvirt instance string [System.Windows.Forms]System.Windows.Forms.FileDialog::get_FileName()
0x6aea9  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetControlText(class [System.Windows.Forms]System.Windows.Forms.Control ctl, string val)
0x6aeae  ldloc.0
0x6aeaf  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0x6aeb4  ret
```
