# Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl::GetTaskXmlFromFile

- ea: `0x7d110`
- end: `0x7d1d7`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl::GetTaskXmlFromFile`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x7d0d0`

## callees

- `0x12ed0`
- `0x133f0`
- `0x7d110`

## string_xrefs

- `0x7d11b`: `TaskInitialDirectoryForImportExport`
- `0x7d12b`: `TaskFileFiltersForImportExport`
- `0x7d183`: `MessageFileDirectoryNotFound`
- `0x7d195`: `MessageReadFileFileNotFound`
- `0x7d1a7`: `MessageReadFileFileLoad`
- `0x7d1b9`: `MessageFilePathTooLong`

## pseudocode

```c

```

## disassembly

```asm
0x7d110  ldnull
0x7d111  stloc.0
0x7d112  ldnull
0x7d113  stloc.1
0x7d114  newobj   instance void [System.Windows.Forms]System.Windows.Forms.OpenFileDialog::.ctor()
0x7d119  stloc.2
0x7d11a  ldloc.2
0x7d11b  ldstr    aTaskinitialdir_1// "TaskInitialDirectoryForImportExport"
0x7d120  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7d125  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_InitialDirectory(string)
0x7d12a  ldloc.2
0x7d12b  ldstr    aTaskfilefilter_1// "TaskFileFiltersForImportExport"
0x7d130  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7d135  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_Filter(string)
0x7d13a  ldloc.2
0x7d13b  ldc.i4.1
0x7d13c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_FilterIndex(int32)
0x7d141  ldloc.2
0x7d142  ldc.i4.1
0x7d143  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_RestoreDirectory(bool)
0x7d148  ldloc.2
0x7d149  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [System.Windows.Forms]System.Windows.Forms.CommonDialog::ShowDialog()
0x7d14e  ldc.i4.1
0x7d14f  bne.un.s loc_7D1CA
0x7d151  ldloc.2
0x7d152  callvirt instance string [System.Windows.Forms]System.Windows.Forms.FileDialog::get_FileName()
0x7d157  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(string)
0x7d15c  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x7d161  stloc.0
0x7d162  ldloc.2
0x7d163  callvirt instance string [System.Windows.Forms]System.Windows.Forms.FileDialog::get_FileName()
0x7d168  call     string [mscorlib]System.IO.Path::GetFileNameWithoutExtension(string)
0x7d16d  stloc.1
0x7d16e  leave.s  loc_7D1CA
0x7d170  pop
0x7d171  ldstr    aMessagefiletoo// "MessageFileTooLarge"
0x7d176  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7d17b  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x7d180  leave.s  loc_7D1CA
0x7d182  pop
0x7d183  ldstr    aMessagefiledir// "MessageFileDirectoryNotFound"
0x7d188  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7d18d  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x7d192  leave.s  loc_7D1CA
0x7d194  pop
0x7d195  ldstr    aMessagereadfil// "MessageReadFileFileNotFound"
0x7d19a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7d19f  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x7d1a4  leave.s  loc_7D1CA
0x7d1a6  pop
0x7d1a7  ldstr    aMessagereadfil_0// "MessageReadFileFileLoad"
0x7d1ac  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7d1b1  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x7d1b6  leave.s  loc_7D1CA
0x7d1b8  pop
0x7d1b9  ldstr    aMessagefilepat// "MessageFilePathTooLong"
0x7d1be  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7d1c3  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x7d1c8  leave.s  loc_7D1CA
0x7d1ca  ldloc.2
0x7d1cb  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0x7d1d0  ldarg.2
0x7d1d1  ldloc.0
0x7d1d2  stind.ref
0x7d1d3  ldarg.1
0x7d1d4  ldloc.1
0x7d1d5  stind.ref
0x7d1d6  ret
```
