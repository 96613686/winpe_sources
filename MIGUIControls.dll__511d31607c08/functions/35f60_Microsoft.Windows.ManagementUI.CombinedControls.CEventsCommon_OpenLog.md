# Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::OpenLog

- ea: `0x35f60`
- end: `0x35fe9`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::OpenLog`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x47c20`

## callees

- `0x12ed0`
- `0x12f00`
- `0x15040`
- `0x35f60`
- `0x38880`
- `0x38890`

## string_xrefs

- `0x35f67`: `EventFileFiltersForOpen`
- `0x35f90`: `OpenLogFile`

## pseudocode

```c

```

## disassembly

```asm
0x35f60  newobj   instance void [System.Windows.Forms]System.Windows.Forms.OpenFileDialog::.ctor()
0x35f65  stloc.0
0x35f66  ldloc.0
0x35f67  ldstr    aEventfilefilte// "EventFileFiltersForOpen"
0x35f6c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x35f71  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_Filter(string)
0x35f76  ldloc.0
0x35f77  ldc.i4.1
0x35f78  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_FilterIndex(int32)
0x35f7d  ldloc.0
0x35f7e  ldc.i4.1
0x35f7f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_RestoreDirectory(bool)
0x35f84  ldloc.0
0x35f85  call     string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_CurrentDirectory()
0x35f8a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_InitialDirectory(string)
0x35f8f  ldloc.0
0x35f90  ldstr    aOpenlogfile// "OpenLogFile"
0x35f95  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x35f9a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_Title(string)
0x35f9f  call     class Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::get_Console()
0x35fa4  ldloc.0
0x35fa5  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.IUIConsole::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.CommonDialog dlg)
0x35faa  stloc.1
0x35fab  ldc.i4.1
0x35fac  ldloc.1
0x35fad  bne.un.s loc_35FE3
0x35faf  ldloc.0
0x35fb0  callvirt instance string [System.Windows.Forms]System.Windows.Forms.FileDialog::get_FileName()
0x35fb5  ldc.i4.0
0x35fb6  ldloc.0
0x35fb7  callvirt instance string [System.Windows.Forms]System.Windows.Forms.FileDialog::get_FileName()
0x35fbc  callvirt instance int32 [mscorlib]System.String::get_Length()
0x35fc1  ldloc.0
0x35fc2  callvirt instance string [System.Windows.Forms]System.Windows.Forms.FileDialog::get_FileName()
0x35fc7  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x35fcc  callvirt instance int32 [mscorlib]System.String::get_Length()
0x35fd1  sub
0x35fd2  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x35fd7  call     void Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::set_CurrentDirectory(string value)
0x35fdc  ldloc.0
0x35fdd  callvirt instance string [System.Windows.Forms]System.Windows.Forms.FileDialog::get_FileName()
0x35fe2  ret
0x35fe3  ldsfld   string [mscorlib]System.String::Empty
0x35fe8  ret
```
