# Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions::PrintMembers

- ea: `0x4c7e0`
- end: `0x4c880`
- name: `Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions::PrintMembers`
- size: `160`
- prototype: ``
- caller_count: `15`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x4c7a0`
- `0x4d620`
- `0x4d660`
- `0x4de90`
- `0x4ded0`
- `0x4e1e0`
- `0x4e220`
- `0x4e360`
- `0x4e3a0`
- `0x4e5b0`
- `0x4e5f0`
- `0x4e7a0`
- `0x4e7e0`
- `0x4eca0`
- `0x4ece0`

## callees

- `0x4c720`
- `0x4c730`
- `0x4c750`
- `0x4c770`
- `0x4c780`

## string_xrefs

- `0x4c83f`: `, InstallationPath = `
- `0x4c858`: `, KeepWindowsUpdateOn = `

## pseudocode

```c

```

## disassembly

```asm
0x4c7e0  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::EnsureSufficientExecutionStack()
0x4c7e5  ldarg.1
0x4c7e6  ldstr    aSetupexecutabl_1// "SetupExecutableArguments = "
0x4c7eb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4c7f0  pop
0x4c7f1  ldarg.1
0x4c7f2  ldarg.0
0x4c7f3  call     instance class Microsoft.VisualStudio.Setup.Services.Installer.ResumeArguments Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions::get_SetupExecutableArguments()
0x4c7f8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4c7fd  pop
0x4c7fe  ldarg.1
0x4c7ff  ldstr    aInstanceid_1// ", InstanceId = "
0x4c804  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4c809  pop
0x4c80a  ldarg.1
0x4c80b  ldarg.0
0x4c80c  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions::get_InstanceId()
0x4c811  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4c816  pop
0x4c817  ldarg.1
0x4c818  ldstr    aTelemetryconte// ", TelemetryContext = "
0x4c81d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4c822  pop
0x4c823  ldarg.1
0x4c824  ldarg.0
0x4c825  call     instance valuetype Microsoft.VisualStudio.Setup.TelemetryContext Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions::get_TelemetryContext()
0x4c82a  stloc.0
0x4c82b  ldloca.s 0
0x4c82d  constrained. Microsoft.VisualStudio.Setup.TelemetryContext
0x4c833  callvirt instance string [mscorlib]System.Object::ToString()
0x4c838  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4c83d  pop
0x4c83e  ldarg.1
0x4c83f  ldstr    aInstallationpa_2// ", InstallationPath = "
0x4c844  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4c849  pop
0x4c84a  ldarg.1
0x4c84b  ldarg.0
0x4c84c  call     instance string Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions::get_InstallationPath()
0x4c851  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x4c856  pop
0x4c857  ldarg.1
0x4c858  ldstr    aKeepwindowsupd// ", KeepWindowsUpdateOn = "
0x4c85d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4c862  pop
0x4c863  ldarg.1
0x4c864  ldarg.0
0x4c865  call     instance bool Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions::get_KeepWindowsUpdateOn()
0x4c86a  stloc.1
0x4c86b  ldloca.s 1
0x4c86d  constrained. [mscorlib]System.Boolean
0x4c873  callvirt instance string [mscorlib]System.Object::ToString()
0x4c878  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4c87d  pop
0x4c87e  ldc.i4.1
0x4c87f  ret
```
