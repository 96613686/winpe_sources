# Microsoft.Windows.Diagnosis.ManagedHost::RunScript

- ea: `0x330`
- end: `0x516`
- name: `Microsoft.Windows.Diagnosis.ManagedHost::RunScript`
- size: `486`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x200`
- `0x330`

## string_xrefs

- `0x3a6`: `\nfunction Test-Caller {\n    param(\n        [Parameter(Mandatory=$true)]\n        [System.Management.Automation.CallStackFrame[]]\n        $CallStack\n    )\n    $caller = $CallStack[1]\n    $location = $caller.Location\n    Write-Verbose -Message $('caller: ' + $location) -Verbose\n    if ($location -eq '<No file>') {\n        throw 'Invoke-Expression cannot be used in a script'\n    }\n}\n\nfunction Invoke-Expression {\n    [CmdletBinding(HelpUri='https://go.microsoft.com/fwl`
- `0x3e4`: `(?i)(.*(invoke-expression|invoke-command|\$\([\b\s]*iex|\$\([\b\s]*icm|\[char\]).*)|(^[\b\s]*&.*)|(.*;[\b\s]*&.*)|(\[system\.)|("|')`

## pseudocode

```c

```

## disassembly

```asm
0x330  ldnull
0x331  stloc.0
0x332  ldarg.0
0x333  ldfld    class [System.Management.Automation]System.Management.Automation.PSCommand Microsoft.Windows.Diagnosis.ManagedHost::m_SetScriptCommand
0x338  brfalse.s loc_342
0x33a  ldarg.0
0x33b  ldfld    class [System.Management.Automation]System.Management.Automation.PSCommand Microsoft.Windows.Diagnosis.ManagedHost::m_ResetScriptCommand
0x340  brtrue.s loc_398
0x342  ldarg.0
0x343  newobj   instance void [System.Management.Automation]System.Management.Automation.PSCommand::.ctor()
0x348  ldstr    aSetLocation// "set-location"
0x34d  call     instance class [System.Management.Automation]System.Management.Automation.PSCommand [System.Management.Automation]System.Management.Automation.PSCommand::AddCommand(string)
0x352  stfld    class [System.Management.Automation]System.Management.Automation.PSCommand Microsoft.Windows.Diagnosis.ManagedHost::m_SetScriptCommand
0x357  ldarg.0
0x358  ldfld    class [System.Management.Automation]System.Management.Automation.PSCommand Microsoft.Windows.Diagnosis.ManagedHost::m_SetScriptCommand
0x35d  ldstr    aPath// "Path"
0x362  call     string [mscorlib]System.IO.Directory::GetCurrentDirectory()
0x367  callvirt instance class [System.Management.Automation]System.Management.Automation.PSCommand [System.Management.Automation]System.Management.Automation.PSCommand::AddParameter(string, object)
0x36c  pop
0x36d  ldarg.0
0x36e  newobj   instance void [System.Management.Automation]System.Management.Automation.PSCommand::.ctor()
0x373  ldstr    aSetLocation// "set-location"
0x378  call     instance class [System.Management.Automation]System.Management.Automation.PSCommand [System.Management.Automation]System.Management.Automation.PSCommand::AddCommand(string)
0x37d  stfld    class [System.Management.Automation]System.Management.Automation.PSCommand Microsoft.Windows.Diagnosis.ManagedHost::m_ResetScriptCommand
0x382  ldarg.0
0x383  ldfld    class [System.Management.Automation]System.Management.Automation.PSCommand Microsoft.Windows.Diagnosis.ManagedHost::m_ResetScriptCommand
0x388  ldstr    aPath// "Path"
0x38d  ldstr    asc_119E// "\\"
0x392  callvirt instance class [System.Management.Automation]System.Management.Automation.PSCommand [System.Management.Automation]System.Management.Automation.PSCommand::AddParameter(string, object)
0x397  pop
0x398  ldarg.0
0x399  ldfld    class [System.Management.Automation]System.Management.Automation.PSCommand Microsoft.Windows.Diagnosis.ManagedHost::s_LoadPowershellCmdletProxiesCommand
0x39e  brtrue.s loc_3B5
0x3a0  ldarg.0
0x3a1  newobj   instance void [System.Management.Automation]System.Management.Automation.PSCommand::.ctor()
0x3a6  ldstr    aFunctionTestCa// "\r\nfunction Test-Caller {\r\n    param"...
0x3ab  call     instance class [System.Management.Automation]System.Management.Automation.PSCommand [System.Management.Automation]System.Management.Automation.PSCommand::AddScript(string)
0x3b0  stfld    class [System.Management.Automation]System.Management.Automation.PSCommand Microsoft.Windows.Diagnosis.ManagedHost::s_LoadPowershellCmdletProxiesCommand
0x3b5  ldstr    asc_8EC4// "& '"
0x3ba  ldarg.1
0x3bb  ldstr    asc_8ECC// "'"
0x3c0  call     string [mscorlib]System.String::Concat(string, string, string)
0x3c5  stloc.0
0x3c6  ldarg.2
0x3c7  brfalse  loc_480
0x3cc  ldarg.3
0x3cd  brfalse  loc_480
0x3d2  ldarg.2
0x3d3  ldlen
0x3d4  conv.i4
0x3d5  ldarg.3
0x3d6  ldlen
0x3d7  conv.i4
0x3d8  beq.s    loc_3E4
0x3da  ldc.i4   0x803C0103
0x3df  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x3e4  ldstr    aIInvokeExpress// "(?i)(.*(invoke-expression|invoke-comman"...
0x3e9  ldc.i4.s 9
0x3eb  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x3f0  stloc.1
0x3f1  ldc.i4.0
0x3f2  stloc.2
0x3f3  br.s     loc_473
0x3f5  ldarg.3
0x3f6  ldloc.2
0x3f7  ldelem.ref
0x3f8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3fd  brtrue.s loc_45B
0x3ff  ldloc.1
0x400  ldarg.3
0x401  ldloc.2
0x402  ldelem.ref
0x403  callvirt instance class [System]System.Text.RegularExpressions.MatchCollection [System]System.Text.RegularExpressions.Regex::Matches(string)
0x408  callvirt instance int32 [System]System.Text.RegularExpressions.MatchCollection::get_Count()
0x40d  ldc.i4.0
0x40e  ble.s    loc_41A
0x410  ldc.i4   0x803C0103
0x415  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x41a  ldarg.3
0x41b  ldloc.2
0x41c  ldarg.3
0x41d  ldloc.2
0x41e  ldelem.ref
0x41f  call     string [System.Management.Automation]System.Management.Automation.Language.CodeGeneration::EscapeSingleQuotedStringContent(string)
0x424  stelem.ref
0x425  ldc.i4.6
0x426  newarr   [mscorlib]System.String
0x42b  dup
0x42c  ldc.i4.0
0x42d  ldloc.0
0x42e  stelem.ref
0x42f  dup
0x430  ldc.i4.1
0x431  ldstr    asc_8FDA// " -"
0x436  stelem.ref
0x437  dup
0x438  ldc.i4.2
0x439  ldarg.2
0x43a  ldloc.2
0x43b  ldelem.ref
0x43c  stelem.ref
0x43d  dup
0x43e  ldc.i4.3
0x43f  ldstr    asc_8FE0// " '"
0x444  stelem.ref
0x445  dup
0x446  ldc.i4.4
0x447  ldarg.3
0x448  ldloc.2
0x449  ldelem.ref
0x44a  stelem.ref
0x44b  dup
0x44c  ldc.i4.5
0x44d  ldstr    asc_8ECC// "'"
0x452  stelem.ref
0x453  call     string [mscorlib]System.String::Concat(string[])
0x458  stloc.0
0x459  br.s     loc_46F
0x45b  ldloc.0
0x45c  ldstr    asc_8FDA// " -"
0x461  ldarg.2
0x462  ldloc.2
0x463  ldelem.ref
0x464  ldstr    asc_8FE6// " ''"
0x469  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x46e  stloc.0
0x46f  ldloc.2
0x470  ldc.i4.1
0x471  add
0x472  stloc.2
0x473  ldloc.2
0x474  conv.u8
0x475  ldarg.2
0x476  ldlen
0x477  conv.i4
0x478  conv.i8
0x479  blt      loc_3F5
0x47e  br.s     loc_490
0x480  ldarg.2
0x481  brtrue.s loc_486
0x483  ldarg.3
0x484  brfalse.s loc_490
0x486  ldc.i4   0x803C0103
0x48b  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x490  ldarg.0
0x491  ldfld    class [System.Management.Automation]System.Management.Automation.PowerShell Microsoft.Windows.Diagnosis.ManagedHost::m_Ps
0x496  ldarg.0
0x497  ldfld    class [System.Management.Automation]System.Management.Automation.PSCommand Microsoft.Windows.Diagnosis.ManagedHost::m_SetScriptCommand
0x49c  callvirt instance void [System.Management.Automation]System.Management.Automation.PowerShell::set_Commands(class [System.Management.Automation]System.Management.Automation.PSCommand)
0x4a1  ldarg.0
0x4a2  ldarg.0
0x4a3  ldfld    class [System.Management.Automation]System.Management.Automation.PowerShell Microsoft.Windows.Diagnosis.ManagedHost::m_Ps
0x4a8  call     instance void Microsoft.Windows.Diagnosis.ManagedHost::ExecuteCommand(class [System.Management.Automation]System.Management.Automation.PowerShell ps)
0x4ad  ldarg.0
0x4ae  ldfld    class [System.Management.Automation]System.Management.Automation.PowerShell Microsoft.Windows.Diagnosis.ManagedHost::m_Ps
0x4b3  ldarg.0
0x4b4  ldfld    class [System.Management.Automation]System.Management.Automation.PSCommand Microsoft.Windows.Diagnosis.ManagedHost::s_LoadPowershellCmdletProxiesCommand
0x4b9  callvirt instance void [System.Management.Automation]System.Management.Automation.PowerShell::set_Commands(class [System.Management.Automation]System.Management.Automation.PSCommand)
0x4be  ldarg.0
0x4bf  ldarg.0
0x4c0  ldfld    class [System.Management.Automation]System.Management.Automation.PowerShell Microsoft.Windows.Diagnosis.ManagedHost::m_Ps
0x4c5  call     instance void Microsoft.Windows.Diagnosis.ManagedHost::ExecuteCommand(class [System.Management.Automation]System.Management.Automation.PowerShell ps)
0x4ca  ldarg.0
0x4cb  ldfld    class [System.Management.Automation]System.Management.Automation.PowerShell Microsoft.Windows.Diagnosis.ManagedHost::m_Ps
0x4d0  newobj   instance void [System.Management.Automation]System.Management.Automation.PSCommand::.ctor()
0x4d5  callvirt instance void [System.Management.Automation]System.Management.Automation.PowerShell::set_Commands(class [System.Management.Automation]System.Management.Automation.PSCommand)
0x4da  ldarg.0
0x4db  ldfld    class [System.Management.Automation]System.Management.Automation.PowerShell Microsoft.Windows.Diagnosis.ManagedHost::m_Ps
0x4e0  callvirt instance class [System.Management.Automation]System.Management.Automation.PSCommand [System.Management.Automation]System.Management.Automation.PowerShell::get_Commands()
0x4e5  ldloc.0
0x4e6  callvirt instance class [System.Management.Automation]System.Management.Automation.PSCommand [System.Management.Automation]System.Management.Automation.PSCommand::AddScript(string)
0x4eb  pop
0x4ec  ldarg.0
0x4ed  ldarg.0
0x4ee  ldfld    class [System.Management.Automation]System.Management.Automation.PowerShell Microsoft.Windows.Diagnosis.ManagedHost::m_Ps
0x4f3  call     instance void Microsoft.Windows.Diagnosis.ManagedHost::ExecuteCommand(class [System.Management.Automation]System.Management.Automation.PowerShell ps)
0x4f8  ldarg.0
0x4f9  ldfld    class [System.Management.Automation]System.Management.Automation.PowerShell Microsoft.Windows.Diagnosis.ManagedHost::m_Ps
0x4fe  ldarg.0
0x4ff  ldfld    class [System.Management.Automation]System.Management.Automation.PSCommand Microsoft.Windows.Diagnosis.ManagedHost::m_ResetScriptCommand
0x504  callvirt instance void [System.Management.Automation]System.Management.Automation.PowerShell::set_Commands(class [System.Management.Automation]System.Management.Automation.PSCommand)
0x509  ldarg.0
0x50a  ldarg.0
0x50b  ldfld    class [System.Management.Automation]System.Management.Automation.PowerShell Microsoft.Windows.Diagnosis.ManagedHost::m_Ps
0x510  call     instance void Microsoft.Windows.Diagnosis.ManagedHost::ExecuteCommand(class [System.Management.Automation]System.Management.Automation.PowerShell ps)
0x515  ret
```
