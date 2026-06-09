# Microsoft.VisualStudio.Setup.Services.Extensions::TryStartProcess

- ea: `0x113f0`
- end: `0x11474`
- name: `Microsoft.VisualStudio.Setup.Services.Extensions::TryStartProcess`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x280`
- `0x620`
- `0x113f0`
- `0x123b0`
- `0x123e0`
- `0x124a0`
- `0x12540`
- `0x125e0`
- `0x12600`
- `0x12680`
- `0x126a0`

## pseudocode

```c

```

## disassembly

```asm
0x113f0  ldarg.1
0x113f1  ldarg.0
0x113f2  callvirt instance class Microsoft.VisualStudio.Setup.Services.IChildProcess Microsoft.VisualStudio.Setup.Services.IProcessService::CreateProcess()
0x113f7  stind.ref
0x113f8  ldarg.1
0x113f9  ldind.ref
0x113fa  callvirt instance class Microsoft.VisualStudio.Setup.Services.IProcessStartInfo Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x113ff  ldarg.2
0x11400  callvirt instance void Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_FileName(string value)
0x11405  ldarg.1
0x11406  ldind.ref
0x11407  callvirt instance class Microsoft.VisualStudio.Setup.Services.IProcessStartInfo Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x1140c  ldarg.s  4
0x1140e  ldc.i4.0
0x1140f  ceq
0x11411  callvirt instance void Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_CreateNoWindow(bool value)
0x11416  ldarg.3
0x11417  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1141c  brtrue.s loc_1142B
0x1141e  ldarg.1
0x1141f  ldind.ref
0x11420  callvirt instance class Microsoft.VisualStudio.Setup.Services.IProcessStartInfo Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x11425  ldarg.3
0x11426  callvirt instance void Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_Arguments(string value)
0x1142b  ldarg.s  5
0x1142d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11432  brtrue.s loc_11442
0x11434  ldarg.1
0x11435  ldind.ref
0x11436  callvirt instance class Microsoft.VisualStudio.Setup.Services.IProcessStartInfo Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x1143b  ldarg.s  5
0x1143d  callvirt instance void Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_WorkingDirectory(string value)
0x11442  ldarg.1
0x11443  ldind.ref
0x11444  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IProcess::Start()
0x11449  brtrue.s loc_1145C
0x1144b  ldarg.1
0x1144c  ldind.ref
0x1144d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11452  leave.s  loc_11457
0x11454  pop
0x11455  leave.s  loc_11457
0x11457  ldarg.1
0x11458  ldnull
0x11459  stind.ref
0x1145a  ldc.i4.0
0x1145b  ret
0x1145c  ldarg.s  4
0x1145e  brfalse.s loc_11472
0x11460  ldarg.1
0x11461  ldind.ref
0x11462  callvirt instance native int Microsoft.VisualStudio.Setup.Services.IProcess::get_MainWindowHandle()
0x11467  call     valuetype Windows.Win32.Foundation.HWND Windows.Win32.Foundation.HWND::op_Explicit(native int value)
0x1146c  call     valuetype Windows.Win32.Foundation.BOOL Windows.Win32.SetupCommonPInvoke::SetForegroundWindow(valuetype Windows.Win32.Foundation.HWND hWnd)
0x11471  pop
0x11472  ldc.i4.1
0x11473  ret
```
