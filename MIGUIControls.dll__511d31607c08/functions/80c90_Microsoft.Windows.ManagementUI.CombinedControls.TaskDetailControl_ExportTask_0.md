# Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ExportTask_0

- ea: `0x80c90`
- end: `0x80d7e`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TaskDetailControl::ExportTask_0`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x80c60`

## callees

- `0x12ed0`
- `0x133f0`
- `0x645c0`
- `0x646e0`
- `0x7cf40`
- `0x80c90`

## string_xrefs

- `0x80c97`: `TaskInitialDirectoryForImportExport`
- `0x80ca7`: `TaskFileFiltersForImportExport`
- `0x80d4b`: `MessageFileDirectoryNotFound`
- `0x80d27`: `MessageWriteFileNoPermission`
- `0x80d39`: `MessageWriteFileNoPermission`
- `0x80d5d`: `MessageFilePathTooLongException`

## pseudocode

```c

```

## disassembly

```asm
0x80c90  newobj   instance void [System.Windows.Forms]System.Windows.Forms.SaveFileDialog::.ctor()
0x80c95  stloc.0
0x80c96  ldloc.0
0x80c97  ldstr    aTaskinitialdir_1// "TaskInitialDirectoryForImportExport"
0x80c9c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x80ca1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_InitialDirectory(string)
0x80ca6  ldloc.0
0x80ca7  ldstr    aTaskfilefilter_1// "TaskFileFiltersForImportExport"
0x80cac  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x80cb1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_Filter(string)
0x80cb6  ldloc.0
0x80cb7  ldc.i4.1
0x80cb8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_FilterIndex(int32)
0x80cbd  ldloc.0
0x80cbe  ldc.i4.1
0x80cbf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_RestoreDirectory(bool)
0x80cc4  ldloc.0
0x80cc5  ldstr    aXml// "xml"
0x80cca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_DefaultExt(string)
0x80ccf  ldloc.0
0x80cd0  ldc.i4.1
0x80cd1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_AddExtension(bool)
0x80cd6  ldloc.0
0x80cd7  ldarg.1
0x80cd8  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x80cdd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_FileName(string)
0x80ce2  ldloc.0
0x80ce3  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [System.Windows.Forms]System.Windows.Forms.CommonDialog::ShowDialog()
0x80ce8  ldc.i4.1
0x80ce9  bne.un   loc_80D77
0x80cee  ldarg.1
0x80cef  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_XmlText()
0x80cf4  stloc.1
0x80cf5  ldloc.0
0x80cf6  callvirt instance string [System.Windows.Forms]System.Windows.Forms.FileDialog::get_FileName()
0x80cfb  ldc.i4.0
0x80cfc  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0x80d01  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(string, bool, class [mscorlib]System.Text.Encoding)
0x80d06  dup
0x80d07  ldloc.1
0x80d08  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x80d0d  callvirt instance void [mscorlib]System.IO.TextWriter::Close()
0x80d12  leave.s  loc_80D77
0x80d14  pop
0x80d15  ldstr    aMessagefiletoo// "MessageFileTooLarge"
0x80d1a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x80d1f  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x80d24  leave.s  loc_80D77
0x80d26  pop
0x80d27  ldstr    aMessagewritefi// "MessageWriteFileNoPermission"
0x80d2c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x80d31  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x80d36  leave.s  loc_80D77
0x80d38  pop
0x80d39  ldstr    aMessagewritefi// "MessageWriteFileNoPermission"
0x80d3e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x80d43  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x80d48  leave.s  loc_80D77
0x80d4a  pop
0x80d4b  ldstr    aMessagefiledir// "MessageFileDirectoryNotFound"
0x80d50  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x80d55  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x80d5a  leave.s  loc_80D77
0x80d5c  pop
0x80d5d  ldstr    aMessagefilepat_0// "MessageFilePathTooLongException"
0x80d62  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x80d67  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x80d6c  leave.s  loc_80D77
0x80d6e  pop
0x80d6f  ldarg.0
0x80d70  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl::HandleServiceUnavailableException()
0x80d75  leave.s  loc_80D77
0x80d77  ldloc.0
0x80d78  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0x80d7d  ret
```
