# Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction::FileBrowser

- ea: `0x6a600`
- end: `0x6a673`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction::FileBrowser`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x6a920`

## callees

- `0x12ed0`
- `0x13670`
- `0x6a600`

## string_xrefs

- `0x6a607`: `TaskInitialDirectoryForActionLaunchExecutable`
- `0x6a617`: `TaskFileFiltersForActionLaunchExecutable`

## pseudocode

```c

```

## disassembly

```asm
0x6a600  newobj   instance void [System.Windows.Forms]System.Windows.Forms.OpenFileDialog::.ctor()
0x6a605  stloc.0
0x6a606  ldloc.0
0x6a607  ldstr    aTaskinitialdir// "TaskInitialDirectoryForActionLaunchExec"...
0x6a60c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6a611  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_InitialDirectory(string)
0x6a616  ldloc.0
0x6a617  ldstr    aTaskfilefilter// "TaskFileFiltersForActionLaunchExecutabl"...
0x6a61c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6a621  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_Filter(string)
0x6a626  ldloc.0
0x6a627  ldc.i4.2
0x6a628  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_FilterIndex(int32)
0x6a62d  ldloc.0
0x6a62e  ldc.i4.1
0x6a62f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_RestoreDirectory(bool)
0x6a634  ldloc.0
0x6a635  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [System.Windows.Forms]System.Windows.Forms.CommonDialog::ShowDialog()
0x6a63a  ldc.i4.1
0x6a63b  bne.un.s loc_6A66C
0x6a63d  ldloc.0
0x6a63e  callvirt instance string [System.Windows.Forms]System.Windows.Forms.FileDialog::get_FileName()
0x6a643  stloc.1
0x6a644  ldloc.1
0x6a645  ldc.i4.s 0x20
0x6a647  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x6a64c  ldc.i4.0
0x6a64d  blt.s    loc_6A660
0x6a64f  ldstr    asc_AC654// "\""
0x6a654  ldloc.1
0x6a655  ldstr    asc_AC654// "\""
0x6a65a  call     string [mscorlib]System.String::Concat(string, string, string)
0x6a65f  stloc.1
0x6a660  ldarg.0
0x6a661  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlExecutableAction::textBoxProgramPath
0x6a666  ldloc.1
0x6a667  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SetControlText(class [System.Windows.Forms]System.Windows.Forms.Control ctl, string val)
0x6a66c  ldloc.0
0x6a66d  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0x6a672  ret
```
