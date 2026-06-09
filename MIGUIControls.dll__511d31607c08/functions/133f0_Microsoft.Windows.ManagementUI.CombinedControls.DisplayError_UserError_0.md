# Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError_0

- ea: `0x133f0`
- end: `0x13424`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError_0`
- size: `52`
- prototype: ``
- caller_count: `56`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14790`
- `0x16040`
- `0x5d860`
- `0x5d890`
- `0x5d8c0`
- `0x5d8f0`
- `0x64a20`
- `0x64a80`
- `0x64ba0`
- `0x64c50`
- `0x65050`
- `0x65450`
- `0x65510`
- `0x655e0`
- `0x656f0`
- `0x65990`
- `0x65a30`
- `0x65b10`
- `0x65c70`
- `0x65cd0`
- `0x65e90`
- `0x66580`
- `0x669f0`
- `0x67080`
- `0x672b0`
- `0x676c0`
- `0x67780`
- `0x67820`
- `0x67ad0`
- `0x683d0`
- `0x6ee60`
- `0x7ce60`
- `0x7d110`
- `0x7d260`
- `0x7db80`
- `0x80780`
- `0x80ae0`
- `0x80bd0`
- `0x80c90`
- `0x80df0`
- `0x86f20`
- `0x87110`
- `0x87310`
- `0x878d0`
- `0x87d10`
- `0x89170`
- `0x89280`
- `0x8a150`
- `0x8a560`
- `0x8aca0`

## callees

- `0x12ed0`
- `0x133f0`
- `0x134b0`

## string_xrefs

- `0x133f2`: `ApplicationTaskScheduler`
- `0x13409`: `ApplicationTaskScheduler`

## pseudocode

```c

```

## disassembly

```asm
0x133f0  ldc.i4.0
0x133f1  ldarg.0
0x133f2  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x133f7  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x133fc  ldc.i4.0
0x133fd  ldc.i4.0
0x133fe  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::ShowMessageBox(bool parentIsModal, string message, string caption, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons buttons, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon icon)
0x13403  pop
0x13404  leave.s  loc_1341D
0x13406  pop
0x13407  ldc.i4.1
0x13408  ldarg.0
0x13409  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x1340e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x13413  ldc.i4.0
0x13414  ldc.i4.0
0x13415  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::ShowMessageBox(bool parentIsModal, string message, string caption, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxButtons buttons, valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon icon)
0x1341a  pop
0x1341b  leave.s  loc_1341D
0x1341d  ldarg.0
0x1341e  call     void [System]System.Diagnostics.Trace::WriteLine(string)
0x13423  ret
```
