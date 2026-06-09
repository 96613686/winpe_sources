# Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::ExportLog

- ea: `0x35b70`
- end: `0x35c6b`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::ExportLog`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x2c720`
- `0x47e00`

## callees

- `0x13590`
- `0x35b70`
- `0x35c70`
- `0x4d230`

## string_xrefs

- `0x35b8a`: `CEventsCommon`
- `0x35bac`: `CEventsCommon`
- `0x35c05`: `CEventsCommon`
- `0x35c3e`: `CEventsCommon`
- `0x35b90`: `ExportLog: Deleted existing file '{0}'`
- `0x35bb2`: `Warning: ExportLog: Unable to delete existing file '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x35b70  ldarg.s  4
0x35b72  brfalse.s loc_35B7C
0x35b74  ldarg.0
0x35b75  ldarg.2
0x35b76  call     void Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::ExportLogUsingTracerpt(string EtlFilePath, string fileName)
0x35b7b  ret
0x35b7c  ldarg.2
0x35b7d  call     bool [mscorlib]System.IO.File::Exists(string)
0x35b82  brfalse.s loc_35BCD
0x35b84  ldarg.2
0x35b85  call     void [mscorlib]System.IO.File::Delete(string)
0x35b8a  ldstr    aCeventscommon// "CEventsCommon"
0x35b8f  ldnull
0x35b90  ldstr    aExportlogDelet// "ExportLog: Deleted existing file '{0}'"
0x35b95  ldc.i4.1
0x35b96  newarr   [mscorlib]System.Object
0x35b9b  dup
0x35b9c  ldc.i4.0
0x35b9d  ldarg.2
0x35b9e  stelem.ref
0x35b9f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x35ba4  call     void [System]System.Diagnostics.Trace::WriteLine(string, string)
0x35ba9  leave.s  loc_35BCD
0x35bab  pop
0x35bac  ldstr    aCeventscommon// "CEventsCommon"
0x35bb1  ldnull
0x35bb2  ldstr    aWarningExportl// "Warning: ExportLog: Unable to delete ex"...
0x35bb7  ldc.i4.1
0x35bb8  newarr   [mscorlib]System.Object
0x35bbd  dup
0x35bbe  ldc.i4.0
0x35bbf  ldarg.2
0x35bc0  stelem.ref
0x35bc1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x35bc6  call     void [System]System.Diagnostics.Trace::WriteLine(string, string)
0x35bcb  leave.s  loc_35BCD
0x35bcd  ldarg.0
0x35bce  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::ExternalFilePrefix
0x35bd3  ldc.i4.5
0x35bd4  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x35bd9  brfalse.s loc_35BF1
0x35bdb  ldc.i4.2
0x35bdc  stloc.0
0x35bdd  ldarg.0
0x35bde  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::ExternalFilePrefix
0x35be3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x35be8  callvirt instance string [mscorlib]System.String::Substring(int32)
0x35bed  starg.s  0
0x35bef  br.s     loc_35BF3
0x35bf1  ldc.i4.1
0x35bf2  stloc.0
0x35bf3  ldarg.3
0x35bf4  ldarg.0
0x35bf5  ldarg.1
0x35bf6  ldarg.2
0x35bf7  ldloc.0
0x35bf8  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::ExportLog(native int session, [hasfieldmarshal] string channelPath, [hasfieldmarshal] string query, [hasfieldmarshal] string targetFilePath, [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.ExportLogFlags flags)
0x35bfd  brtrue.s loc_35C3E
0x35bff  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor()
0x35c04  stloc.1
0x35c05  ldstr    aCeventscommon// "CEventsCommon"
0x35c0a  ldnull
0x35c0b  ldstr    aErrorExportlog// "Error: ExportLog: Export failed from {0"...
0x35c10  ldc.i4.3
0x35c11  newarr   [mscorlib]System.Object
0x35c16  dup
0x35c17  ldc.i4.0
0x35c18  ldloc.0
0x35c19  box      Microsoft.Windows.ManagementUI.CombinedControls.ExportLogFlags
0x35c1e  stelem.ref
0x35c1f  dup
0x35c20  ldc.i4.1
0x35c21  ldarg.0
0x35c22  stelem.ref
0x35c23  dup
0x35c24  ldc.i4.2
0x35c25  ldarg.2
0x35c26  stelem.ref
0x35c27  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x35c2c  call     void [System]System.Diagnostics.Trace::WriteLine(string, string)
0x35c31  ldstr    aEvtexportlog// "EvtExportLog"
0x35c36  ldloc.1
0x35c37  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Exception(string prefix, class [System]System.ComponentModel.Win32Exception ex)
0x35c3c  ldloc.1
0x35c3d  throw
0x35c3e  ldstr    aCeventscommon// "CEventsCommon"
0x35c43  ldnull
0x35c44  ldstr    aExportlogExpor// "ExportLog: Exported from {0} '{1}' to '"...
0x35c49  ldc.i4.3
0x35c4a  newarr   [mscorlib]System.Object
0x35c4f  dup
0x35c50  ldc.i4.0
0x35c51  ldloc.0
0x35c52  box      Microsoft.Windows.ManagementUI.CombinedControls.ExportLogFlags
0x35c57  stelem.ref
0x35c58  dup
0x35c59  ldc.i4.1
0x35c5a  ldarg.0
0x35c5b  stelem.ref
0x35c5c  dup
0x35c5d  ldc.i4.2
0x35c5e  ldarg.2
0x35c5f  stelem.ref
0x35c60  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x35c65  call     void [System]System.Diagnostics.Trace::WriteLine(string, string)
0x35c6a  ret
```
