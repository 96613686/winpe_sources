# Microsoft.EventViewer.SnapIn.ViewerCommon::HandleException

- ea: `0x9120`
- end: `0x91a9`
- name: `Microsoft.EventViewer.SnapIn.ViewerCommon::HandleException`
- size: `137`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x8d0`
- `0x9e0`
- `0x1ae0`
- `0x1c40`
- `0x3050`
- `0x3110`
- `0x31d0`
- `0x3280`
- `0x3c50`
- `0x3e60`
- `0x3ed0`
- `0x4520`
- `0x4940`
- `0x6810`
- `0x6960`
- `0x6f20`
- `0x7700`
- `0x7810`

## callees

- `0x9120`
- `0xa7b0`

## pseudocode

```c

```

## disassembly

```asm
0x9120  ldc.i4.0
0x9121  stloc.0
0x9122  ldarg.0
0x9123  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ExceptionAction [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException::get_ActionForException()
0x9128  stloc.3
0x9129  ldloc.3
0x912a  switch   loc_913D, loc_9178, loc_916E
0x913b  br.s     loc_91A7
0x913d  ldc.i4.1
0x913e  stloc.0
0x913f  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::.ctor()
0x9144  stloc.1
0x9145  ldloc.1
0x9146  ldarg.0
0x9147  callvirt instance string [mscorlib]System.Exception::get_Message()
0x914c  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Text(string)
0x9151  ldloc.1
0x9152  ldc.i4.s 0x10
0x9154  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon)
0x9159  ldloc.1
0x915a  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ViewerName()
0x915f  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Caption(string)
0x9164  ldarg.1
0x9165  ldloc.1
0x9166  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console::ShowDialog(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters)
0x916b  pop
0x916c  br.s     loc_91A7
0x916e  ldarg.0
0x916f  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIException::TraceException()
0x9174  ldc.i4.1
0x9175  stloc.0
0x9176  br.s     loc_91A7
0x9178  ldc.i4.0
0x9179  stloc.0
0x917a  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::.ctor()
0x917f  stloc.2
0x9180  ldloc.2
0x9181  ldarg.0
0x9182  callvirt instance string [mscorlib]System.Exception::get_Message()
0x9187  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Text(string)
0x918c  ldloc.2
0x918d  ldc.i4.s 0x10
0x918f  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Icon(valuetype [System.Windows.Forms]System.Windows.Forms.MessageBoxIcon)
0x9194  ldloc.2
0x9195  call     string Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ViewerName()
0x919a  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters::set_Caption(string)
0x919f  ldarg.1
0x91a0  ldloc.2
0x91a1  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.Console::ShowDialog(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Advanced.MessageBoxParameters)
0x91a6  pop
0x91a7  ldloc.0
0x91a8  ret
```
